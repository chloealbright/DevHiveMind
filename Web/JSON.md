---
tags:
  - web
  - data
author:
  - jacgit18
Comments: This documentation discusses JSON.
Status: Capture
Started: 
EditDate: 2024-01-30
Relates:
---
### Working with JSON

- **Data Interchange:** JSON is utilized for data interchange, enabling communication between systems that may use different programming languages.

- **Syntax and Exchange:** The syntax of JSON allows for the storage and exchange of data, presented as text in JavaScript Object Notation. This format is universally readable across various programming languages.

- **JSON Methods:** Objects can be encapsulated using the `JSON.parse` or `JSON.stringify` methods. 
  - `JSON.stringify(object)` is used before making requests to servers or databases (via HTTP methods like GET, POST, PUT, or DELETE).
  - Upon receiving data in the browser, `JSON.parse` is applied for processing.

- **Parsing Process:**
  - **Request to Server/DB:** Object is converted to a string using `JSON.stringify` before sending.
  - **Browser Reception:** Upon receiving data, `JSON.parse` is employed to convert the string back to an object.

- **Dealing with JSON Order:**
  - JSON order preservation is inherent; re-parsing may be necessary for specific scenarios, such as reordering keys (`JSON.stringify(JSON.parse(jsonVar))` or `JSON.parse(JSON.stringify(jsonVar))`).

- **Manipulating JSON:**
  - JSON is a protected primitive string; to alter its order, it's converted to an object using `JSON.parse` for mutability. 
  - After manipulation, `JSON.stringify` is used to revert it to a string.

### JSONP

JSONP, or JSON with Padding, addresses cross-domain policy issues when requesting files from external domains. Leveraging the script tag instead of XMLHttpRequest, JSONP facilitates cross-domain data retrieval by embedding the response within a function call, overcoming typical cross-origin limitations.