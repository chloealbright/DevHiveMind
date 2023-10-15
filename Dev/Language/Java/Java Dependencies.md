Use snapshot dependencies in dev but not production


Use Kotlin **DSL**(Domain-Specific Language) over Groovy



Both Groovy and Kotlin are programming languages that can be used in Gradle scripts, but Kotlin has gained more popularity in recent years for Gradle scripting due to its modern features and advantages. However, Groovy is still used in many existing projects and environments. Let's look at the pros and cons of each and when it makes sense to use one over the other:  
  
**Groovy:**  
- **Pros:**  
- **Familiarity:** Groovy has been traditionally used with Gradle, so developers already familiar with Groovy might find it more comfortable.  
- **Simplicity:** Groovy's syntax is simpler and more concise, which can make it easier for simple build scripts.  
- **Integration:** It has a long history of being used with Gradle, and many existing scripts and resources are available.  
  
- **Cons:**  
- **Performance:** Groovy scripts can be slower compared to Kotlin due to the dynamic nature of Groovy.  
- **Less Modern:** Groovy lacks some modern programming language features present in Kotlin.  
  
**Kotlin:**  
- **Pros:**  
- **Performance:** Kotlin is generally faster than Groovy due to its statically typed nature.  
- **Type Safety:** Kotlin provides strong type checking and safety, which can help prevent certain types of errors.  
- **Modern Features:** Kotlin includes modern language features, better null safety, lambdas, and more.  
  
- **Cons:**  
- **Learning Curve:** Developers new to Kotlin might require some time to get accustomed to its syntax.  
- **Integration:** While Kotlin's integration with Gradle is good, there might be more resources and documentation available for Groovy-based Gradle scripts.  
  
**When to Use Each:**  
- **Use Groovy:** If you're working on an existing project with Groovy-based build scripts, it might make sense to continue using Groovy to maintain consistency. Additionally, for simple build scripts where performance isn't a critical factor, Groovy can be a straightforward choice.  
  
- **Use Kotlin:** For new projects or projects where performance is a concern, using Kotlin can be beneficial. Kotlin's modern features and improved type safety make it a better choice for complex build scripts. If you're already familiar with Kotlin or interested in learning it, using it for Gradle scripting can be a good opportunity.  
  
In the end, the choice between Groovy and Kotlin for Gradle scripting depends on factors like the nature of your project, team familiarity, performance requirements, and your own preferences as a developer. While Kotlin is becoming more popular, both languages can still be effectively used for Gradle scripting based on the specific needs of your project.