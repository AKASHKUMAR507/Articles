# Articles by Akash Garg

## Developer Articles

1. [Day 0: Node.js Basics](#day-0-nodejs-basics)
2. [Day 1: Node.js Basics](#day-1-nodejs-basics)
3. [Day 2: Node.js Modules](#day-2-nodejs-modules)
<!-- 4. [Day 3: Node.js Modules](#day-3-nodejs-modules)
5. [Day 4: Node.js Basics](#day-4-nodejs-basics)
6. [Day 5: Node.js Basics](#day-5-nodejs-basics)
7. [Day 6: Node.js Basics](#day-6-nodejs-basics)
8. [Day 7: Node.js Basics](#day-7-nodejs-basics)
9. [Day 8: Node.js Basics](#day-8-nodejs-basics)
10. [Day 9: Node.js Basics](#day-9-nodejs-basics) -->

##

<!-- ## Day 0: Node.js Basics
Content for Day 0...

## Day 1: Node.js Basics
Content for Day 1... -->

# Day 2: Node.js Modules

**1. What is a module?**

* A module is just a file or a piece of code you can reuse.  
* Think of it as a Lego block — you build small blocks (modules) and connect them to create big applications.

* **Node.js has 3 types of modules:**

    + Built-in modules (e.g., fs, http, os).  
    + Custom modules (your own files).  
    + Third-party modules (installed via npm). 



**2. Built-in Modules**

* Example: os module

```javascript
const os = require('os');

console.log("OS Platform:", os.platform());
console.log("CPU Architecture:", os.arch());
console.log("Total Memory:", os.totalmem());
console.log("Free Memory:", os.freemem());
```

* Example: fs module (File System)

```javascript
const fs = require('fs');

// Create a new file
fs.writeFileSync('day2.txt', 'Learning Node.js Modules!');

// Read the file
const data = fs.readFileSync('day2.txt', 'utf-8');
console.log(data);

```
NOTE: 👉 Takeaway: Node already gives you many tools. You just need to know how to use them!

**3. Creating Your Own (Custom) Module**

math.js

```javascript
function add(a, b) {
  return a + b;
}

function multiply(a, b) {
  return a * b;
}

// Export functions
module.exports = { add, multiply };

```
Use in app.js

```javascript
const math = require('./math');

console.log(math.add(5, 3));       // 8
console.log(math.multiply(4, 6));  // 24

//👉 Notice how require('./math') loads your own file.
// The path is relative to the current file.
```

**4. Third-Party Modules (Intro to npm)**
* Node has npm (Node Package Manager) built-in.
* You can install libraries from npm registry.

##### Example: Install chalk (for colored console logs):

```base
npm init -y   # initialize project
npm install chalk  # install chalk
```
##### NOTE: (# initialize project) this is a comment in the code block, not a command to run in the terminal. It's just a note for the reader to understand what the command does.


How to use it

```javascript
const chalk = require('chalk');

console.log(chalk.green("Hello in Green!"));
console.log(chalk.blue("Hello in Blue!"));
```

**5. Key Takeaways**
* Node.js is a runtime environment for JavaScript outside the browser.
* It uses the V8 engine to execute JavaScript code on the server side.
* npm (Node Package Manager) allows you to install and manage third-party libraries easily.
* You can create your own modules and export functions or objects from them.
* Use `require` to import modules in Node.js.
* Use `module.exports` to export functions or objects from your modules.
* Node.js is widely used for building server-side applications, APIs, and real-time applications.
* Node.js is modular by design.
* You can use built-in modules, custom modules, and npm modules.
* Reusability & modularity keep projects clean and organized.


<!-- ## Day 3: Node.js Basics
Content for Day 3...

## Day 4: Node.js Basics
Content for Day 4...

## Day 5: Node.js Basics
Content for Day 5... -->

<!-- ## Day 6: Node.js Basics
Content for Day 6...

## Day 7: Node.js Basics
Content for Day 7...

## Day 8: Node.js Basics
Content for Day 8...

## Day 9: Node.js Basics
Content for Day 9...
 -->
