Admin processes: Administrative tasks, such as [[Database Migrations]], [[Data Seeding]], or [[User Management]], that should be kept separate from the main application processes to prevent interference with regular application operations along with separate deployment from the main application . Using Docker allows you to execute administrative processes within a container, ensuring consistency and avoiding environment-specific issues while maintaining separation of concerns ensuring that administrative activities don't impact the stability, performance, maintenance, and security of the main running application.

 
Admin processes are invoked explicitly when needed and are not part of the regular request-handling process. They are separate from the code that handles user requests or performs the primary business logic of the application. These admin processes might be triggered manually or through automated deployment scripts. Another thing that is included in the admin process and codebase relationship is [[Deployment artifacts]]

## Personal understanding

These tasks are typically performed by developers or administrators, and they might require special privileges or access to sensitive resources.

You define admin process but there are general process that would fall under admin process and the role give permission to enact these process. 

Admin processes Can be be described as a codebase where you have guarded routes and define roles in business logic for who can access certain functionality like the whole app or just certain parts of the app or custom internal tools that interact with the main app. you can almost think of it as a microservice in a sense.

![[Twelve Factor App Admin processes]]

