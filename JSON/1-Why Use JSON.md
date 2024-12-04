---
aliases:
  - 1-Why Use JSON?
---
The JSON format is syntactically similar to the code for creating JavaScript objects. Because of this, a JavaScript program can easily convert JSON data into JavaScript objects.

Since the format is text only, JSON data can easily be sent between computers, and used by any programming language.

JavaScript has a built in function for converting JSON strings into JavaScript objects:
`JSON.parse()`
JavaScript also has a built in function for converting an object into a JSON string:
`JSON.stringify()`


You can receive pure text from a server and use it as a JavaScript object.
You can send a JavaScript object to a server in pure text format.
You can work with data as JavaScript objects, with no complicated parsing and translations.


## Storing Data

When storing data, the data has to be a certain format, and regardless of where you choose to store it, _text_ is always one of the legal formats.

JSON makes it possible to store JavaScript objects as text.