---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Given that, among other reasons, The 12-Factor App [recommended a strict separation of config from code](https://12factor.net/config). This practice quickly took hold throughout the developer community commonly through the use of _.env_ (dotenv) files. These are plain text files that store a list of key/value pairs, defining the environment variables required for an application to work, as in the example below.


```java
package com.settermjd.twilio.envvars;

import io.github.cdimascio.dotenv.Dotenv;
import io.github.cdimascio.dotenv.DotenvException;

public class Main {
    public static void main(String[] args) {
        Dotenv dotenv = null;
        dotenv = Dotenv.configure().load();
        System.out.println(String.format(
            "Hello World. Shell is: %s. Name is: %s",
            System.getenv("SHELL"),
            dotenv.get("NAME")
        ));
    }
}
```

