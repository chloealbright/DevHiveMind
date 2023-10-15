Admin processes: Administrative tasks, such as [[Database Migrations]], [[Data Seeding]], or [[User Management]], that should be kept separate from the main application processes to prevent interference with regular application operations along with separate deployment from the main application . Using Docker allows you to execute administrative processes within a container, ensuring consistency and avoiding environment-specific issues while maintaining separation of concerns ensuring that administrative activities don't impact the stability, performance, maintenance, and security of the main running application.

 
Admin processes are invoked explicitly when needed and are not part of the regular request-handling process. They are separate from the code that handles user requests or performs the primary business logic of the application. These admin processes might be triggered manually or through automated deployment scripts. Another thing that is included in the admin process and codebase relationship is [[Deployment artifacts]]

## Personal understanding

These tasks are typically performed by developers or administrators, and they might require special privileges or access to sensitive resources.

You define admin process but there are general process that would fall under admin process and the role give permission to enact these process. 

Admin processes Can be be described as a codebase where you have guarded routes and define roles in business logic for who can access certain functionality like the whole app or just certain parts of the app or custom internal tools that interact with the main app. you can almost think of it as a microservice in a sense.





## Official Description
### Run admin/management tasks as one-off processes

The [process formation](https://12factor.net/concurrency) is the array of processes that are used to do the app’s regular business (such as handling web requests) as it runs. Separately, developers will often wish to do one-off administrative or maintenance tasks for the app, such as:

- Running database migrations (e.g. `manage.py migrate` in Django, `rake db:migrate` in Rails).
- Running a console (also known as a [REPL](http://en.wikipedia.org/wiki/Read-eval-print_loop) shell) to run arbitrary code or inspect the app’s models against the live database. Most languages provide a REPL by running the interpreter without any arguments (e.g. `python` or `perl`) or in some cases have a separate command (e.g. `irb` for Ruby, `rails console` for Rails).
- Running one-time scripts committed into the app’s repo (e.g. `php scripts/fix_bad_records.php`).

One-off admin processes should be run in an identical environment as the regular [long-running processes](https://12factor.net/processes) of the app. They run against a [release](https://12factor.net/build-release-run), using the same [codebase](https://12factor.net/codebase) and [config](https://12factor.net/config) as any process run against that release. Admin code must ship with application code to avoid synchronization issues.

The same [dependency isolation](https://12factor.net/dependencies) techniques should be used on all process types. For example, if the Ruby web process uses the command `bundle exec thin start`, then a database migration should use `bundle exec rake db:migrate`. Likewise, a Python program using Virtualenv should use the vendored `bin/python` for running both the Tornado webserver and any `manage.py` admin processes.

Twelve-factor strongly favors languages which provide a REPL shell out of the box, and which make it easy to run one-off scripts. In a local deploy, developers invoke one-off admin processes by a direct shell command inside the app’s checkout directory. In a production deploy, developers can use ssh or other remote command execution mechanism provided by that deploy’s execution environment to run such a process.