



## L — iskov Substitution Principle

A super class can be replaced by any of it’s inheriting sub classes at any parts of the system without any change in the code.

It means that the sub classes should extend the functionality of the super class without overriding it.

That’s why we’ve mentioned ealier in [Class Diagram](https://medium.com/omarelgabrys-blog/e7535090824c) that it’s not a good case practice to override the methods of the super class in inheritance.

## I — nterface Segregation Principle

==Interfaces should be specific rather than doing many and different things.==

That’s because any implementing class will only implement the specific needed interfaces rather than being forced to implement methods that it doesn’t need it.

So, large interfaces should be decomposed into smaller, more specific ones.

## D — ependency Inversion Principle

Try to minimize the dependency between objects by using abstraction.

If for example you have a _App_ class that depends on very specialized classes; _Database_ and _Mail_ (dependencies).

Instead, we could have _App_ object that deals with _Service_ class, which is more abstract, rather than something very specific. So, now the _App_ class is not dependent on the concrete classes, but on abstraction.

And the benefit of that is we are able to replace and extend the functionality of _Service_ class without changing the _App_ class at all.

Perhaps we can replace the _Database_ and _Mail_ classes, or add additional classes like _Logger_ and _Auth_ as well.