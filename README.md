# Articles by Akash Garg

## Developer Articles

1. [Day 0: Node.js Getting Started with Node.js](#day-0-getting-started-with-nodejs)
2. [Day 1: Node.js Writing and Running Code in Node.js](#day-1-writing-and-running-code-in-nodejs)
3. [Day 2: Node.js Modules](#day-2-nodejs-modules)
4. [Day 3: Node.js File System (fs) Module in Node.js](#day-3-nodejs-file-system-fs-module-in-nodejs)
5. [Day 4: Events & EventEmitter in Node.js](#day-4-events-and-eventemitter-in-nodejs)
6. [Day 5: Building an HTTP Server in Node.js](#day-5-building-an-http-server-in-nodejs)
7. [Day 6: Serving Static Files in Node.js](#day-6-serving-static-files-in-nodejs)
<!-- 8. [Day 7: Node.js Basics](#day-7-nodejs-basics) -->
<!-- 9. [Day 8: Node.js Basics](#day-8-nodejs-basics) -->
<!-- 10. [Day 9: Node.js Basics](#day-9-nodejs-basics) -->

##
<!-- =======================================Day 0========================= -->
## Day 0: Getting Started with Node.js
**What is Node.js?**
* Node.js is not a programming language.
* It's a JavaScript runtime built on Google Chrome's V8 engine.
* It lets you run JavaScript outside the browser, mainly on the server.

##### 👉 Simple analogy:
* Browser = Kitchen where JS can only cook snacks (Frontend).
* Node.js = Open kitchen + delivery service where JS can now cook full meals (backend)

**Why Node.js**
* Fast: Non-blocking I/O., powered by V8.Fast: Non-blocking I/O., powered by V8.
* Scalable: Handles thousands of requests with event-driven architecture.
* Real-world users: Netflix, PayPal, Uber, LinkedIn

**Prerequisite**
#
* Basic JavaScript knowledge (variables, functions, async/await)
* Understanding of basic command line
* Curious to build the things. 🚀

**Installing Node.js**

1. Go to https://nodejs.org/en/download.
2. Download the LTS (Long-Term Support) version.
3. Install with default settings.
* Verify installation:
```base
  node -v
  npm -v
```
* node -v: shows Node version.
* npm -v: shows package manager version

**First Program**
* Create a file called

app.js:
```javascript
  console.log('Hello, World!');
```
Run it:
```base
  node app.js
```
Output:
```base
  Hello, World!
```

**Key Takeaways**
#

* Node.js allows JavaScript to run on the server.
* It's fast, scalable, and widely used in production.
* Installing Node.js gives you access to both node and npm.
* You just ran your first Node.js program. 🎉

<!-- =======================================Day 1========================= -->

## Day 1: Writing and Running Code in Node.js

**Hello World**
* Explain again how to create a app.js file
* Add more than one line:
```javascript
  console.log('Hello, World!');
  console.log('This is my first Node.js program');
```

* Show how Node executes code. top-to-bottom.

**Using Node REPL (Read-Eval-Print Loop)**

* REPL is like a playground to quickly test JavaScript code without creating files.

Open Terminal -> type:
```terminal
  node
```
Examples inside REPL:
```terminal
  console.log('Hello, World!');
  1 + 1
  10 * 2
```
* Exit REPL by typing `.exit` or pressing `Ctrl + C` twice.

**Difference: Running in REPL vs Running from file**
* REPL -> quick testing, one-liners.
* File -> writing full programs, reusable.

Example:

* In REPL, Let x = 10; disappears when you exit.
* In a file, variables/functions stay saved.

**Node.js as Calculator (Mini Task)**

```javascript
//Encourage reader to try:
console.log(2 + 4);
console.log(29 - 2);
console.log(4 * 7);
console.log(20 / 4);
```

**Command-Line Arguments**

How to pass values from terminal:
greet.js:

```javascript
const args = process.argv.slice(2);
console.log("Hello, " + args[0] + "!");
```

Run:
```base
node greet.js Akash!
```
Output:
```base
Hello, Akash!
```

**Key Takeaways**

* Node.js can be used in two ways: REPL and script file.
* REPL = quick testing, Files = reusable programs.
* You can pass arguments from terminal to scripts.
* You're now ready to explore Node.js modules next. 🚀


<!-- =======================================Day 2========================= -->

## Day 2: Node.js Modules

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


## Day 3: Node.js File System (fs) Module in Node.js

1. **Introduction to the fs Module in Node.js**

* fs stand for File System/
* It allows Node.js to interact with files on your computer.
* You can create, read, update, delete (CURD) files and folder

👉 Think of it as giving JavaScript the power to manage your computer's files.

2. **Importing fs**
    ```javascript
    const fs = require('fs');
    ```
3. **Creating a File**
    ```javascript
    fs.writeFileSync('example.txt', 'Hello, World!');
    // This creates a file named 'example.txt' with the content 'Hello, World!'
    ```
4. **Reading a File**
    ```javascript
    const data = fs.readFileSync('example.txt', 'utf8');
    console.log(data);
    // This reads the content of 'example.txt' and logs it to the console
    ```

* Output

    ```base
      Hello, World!
    ```
5. **Updating(Append) a File**
    ```javascript
    fs.appendFileSync('example.txt', ' This is an appended text');
    // This appends 'This is an appended text' to 'example.txt'
    ```
6. **Deleting a File**
    ```javascript
    fs.unlinkSync('example.txt');
    // This deletes the file 'example.txt'
    ```
7. **Rename File**
    ```javascript
    fs.renameSync('example.txt', 'newExample.txt');
    // This renames 'example.txt' to 'newExample.txt'
    ```
8. **Creating a Folder**
    ```javascript
    fs.mkdirSync('myFolder');
    // This creates a folder named 'myFolder'
    ```

9. **Asynchronous vs Synchronous**

  - **Synchronous Operations**: These operations block the execution of the program until the operation is completed. They are straightforward but can make the application less responsive if used extensively, especially in a server environment where multiple requests need to be handled concurrently.
  - **Asynchronous Operations**: These operations do not block the execution of the program. They use callbacks, promises, or async/await to handle the result once the operation is completed. This makes the application more responsive and efficient, especially in a server environment where multiple requests need to be handled concurrently.

  - Example of Asynchronous File Reading:

    ```javascript
    fs.readFile('example.txt', 'utf8', (err, data) => {
      if (err) {
        console.error('Error reading file:', err);
      } else {
        console.log('File content:', data);
      }
    });

    fs.writeFile('example.txt', 'Hello, World!', (err) => {
      if (err) {
        console.error('Error writing to file:', err);
      } else {
        console.log('File written successfully');
      }
    });
    ```

  - Example of Synchronous File Reading and Writing:
    ```javascript
      fs.readFileSync('example.txt', 'utf8', (err, data) => {
        if (err) {
          console.error('Error reading file:', err);
        } else {
          console.log('File content:', data);
        }
      });


      fs.writeFileSync('example.txt', 'Hello, World!', (err) => {
        if (err) {
          console.error('Error writing to file:', err);
        } else {
          console.log('File written successfully');
        }
      });
    ```

👉 **Difference**
* writeFileSync - blocks the program until done
* writeFile - runs in background, doesn't block other code

👉. **Key Takeaways**
#
* fs module lets you create, read, update, delete files.
* Sync method are easy to use but block execution
* Async method are better for scalable applications.
* Node.js encourages asynchronous programming

👉 Suggested **Day 4:** "Events & EventEmitter in Node.js" (Supper important for understand how Node works under the hood).


<!-- ====================================================== -->
## Day 4: Events And EventEmitter in Node.js

1. **What are Event**
    > An event is an action/occurrence in a program (e.g., user click an button, a file is read, a server receives a request)

    > Node.js uses a **event-driven** architecture, meaning it waits for events and reacts when they happen

👉 Analogy: Think of a radio. It emits signals (events), and you tune in (listen) to act when they happen.

2. **EventEmitter Class**

    > In Node.js, events are handled using the event module.
    > It provides the EventEmitter class to create, file and listen to events.

    Import: 
    ```javascript
      const  EventEmitter = require('event');

      const eventEmitter = new EventEmitter();
    ```  

3. **Basic Example: Emit & Listen**
    ```javascript
      // Create an event listener

      eventEmitter.on('greet', () => {
        console.log('Hello from EventEmitter!');
      })

      //Emit the event
      eventEmitter.emit('greet');


      // Output:
      Hello from EventEmitter!
    ```
 
4. **Passing Data with Events**
    ```javascript
      eventEmitter.on('logout', (message) => {
        console.log(message)
      });

      eventEmitter.emit('logout', 'You are logout.')

      // Output:
      You are logout.
    ```

5. **Multiple Listeners**
    ```javascript
      eventEmitter.on('welcome', () => {
        console.log('Welcome listeners 1')
      })

       eventEmitter.on('welcome', () => {
        console.log('Welcome listeners 2')
      })

      eventEmitter.emit('welcome');

      //Output:
      Welcome listeners 1
      Welcome listeners 2
    ```

6. **Real-World Example: File Event**

    ```javascript
      const fs = require('fs');

      eventEmitter.on('fileCreated', (fileName) => {
        console.log(`A new file was created: ${fileName}`)
      })

      
      fs.writeFileSync('day4.txt', 'EventEmitter example');
      eventEmitter.emit('fileCreated', 'day4.txt');
    ```

7. **Imported Methods**

    * `.on(event, listeners)` -> add a listeners.
    * `.emit(event, data)` -> Trigger the event.
    * `.once(event, listeners)` -> listen only once.
    * `.removeListener(event, listeners)` -> Remove specific listeners.
    * `.removeAllListener(event)` -> Remove all Listeners. 

8. **Key Takeaways**

    * Node.js is event-driven at its code.
    * EventEmitter lets you emit events and listen to them.
    * Events make apps emit asynchronous, scalable, and reactive.
    * Many Node.js core modules (like http, fs, net) are built on EventEmitter.

👉 Suggested Day 5: "Building an HTTP Server in Node.js" (using http module + connecting with EventEmitter).



## Day 5: Building an HTTP Server in Node.js

1. **What is an HTTP Server**

    * HTTP = HyperText Transfer Protocol, the foundation of the web.
    * A server is a program that listens to client requests (like browser requests) and sends back responses (like HTML, JSON, or files).
    * In Node.js the http module is used to create server.

👉 Analogy: Think of a restaurant

* Client = Customer placing order.
* Server = Waiter taking order & bringing food.
* Response = food delivered.

2. **Importing the http Module**

    ```javascript
      const http = require('http');
    ```

3. **Creating a Simple Server**

    ```javascript
      const http = require('http');

      const server = http.createServer((req, res) => {
        res.writeHead(200, {'Content-Type': 'text/plain'});

        res.end(`
          <h1>Welcome to Node.js Server</h1>
          <p>This is served with html response.</p>
        `);
      });
    ```


4. **Sending JSON Response**

    ```javascript
      const http = require('http');

      const server = http.createServer((req, res) => {
        res.writeHead(200, {'Content-Type': 'application/json'});

        res.end(JSON.stringify({
          message: "Hello",
          day: 5
        }));
      });
    ```

5. **Key Takeaways**

    * The `http` module allows Node.js to create servers.
    * `req` = Request Object (contains URL, headers, etc.).
    * `res` = Response object (used to send data back).
    * You can send `text`, `HTML`, or `JSON` responses.
    * Routing helps send different responses for difference URLs

👉 Suggested: **Day 6**: "Serving Static Files with Node.js (HTML, CSS, JS, using fs + http)."



## Day 6: Serving Static Files in Node.js
1. **What Are Static Files?**

    * Static files are that don't change dynamically - e.g., HTML, CSS, JavaScript, images.
    * When you visit a website, your browser requests these files from the server.
    * Node.js can serve them using the fs + http modules.

    Example: 
    
      When you open http://3000/home.html, Node reads that file and sends it to your browser

2. **Setup Folder Structure**
```base
  project/
    ├── server.js
    └── public/
          ├── index.html
          ├── about.html
          ├── style.css
```

3. **Sample HTML File**

public/index.html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Home Page</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>Welcome to My Node.js Static Server</h1>
    <p>This is Day 6 — serving static files.</p>
  </body>
</html>
```

public/style.css

```css
body {
  font-family: Arial, sans-serif;
  background: #f0f0f0;
  color: #333;
  text-align: center;
  padding-top: 40px;
}
```

4. **Create the Server(server.js)**

```javascript
  const http = require('http');
const fs = require('fs');
const path = require('path');

const server = http.createServer((req, res) => {
  // Build file path
  let filePath = path.join(__dirname, 'public', req.url === '/' ? 'index.html' : req.url);

  // Get file extension
  let ext = path.extname(filePath);

  // Default Content Type
  let contentType = 'text/html';

  // Set content type based on file extension
  switch (ext) {
    case '.js':
      contentType = 'text/javascript';
      break;
    case '.css':
      contentType = 'text/css';
      break;
    case '.json':
      contentType = 'application/json';
      break;
    case '.png':
      contentType = 'image/png';
      break;
    case '.jpg':
      contentType = 'image/jpg';
      break;
  }

  // Read and serve the file
  fs.readFile(filePath, (err, content) => {
    if (err) {
      if (err.code === 'ENOENT') {
        res.writeHead(404, { 'Content-Type': 'text/html' });
        res.end('<h1>404: File Not Found</h1>');
      } else {
        res.writeHead(500);
        res.end('Server Error');
      }
    } else {
      res.writeHead(200, { 'Content-Type': contentType });
      res.end(content);
    }
  });
});

server.listen(3000, () => console.log('Server running on http://localhost:3000'));
```

5. **Test it**

Run
```base
  node server.js
```

Open in Browser
  
  * http://localhost:3000/ -> load index.html
  * http://localhost/about.html -> load about.html
  * http://localhost/style.css -> load style.css

6. **Key Takeaways**

  * You can serve HTML, CSS, JS, and image files using Node.js
  * The fs module reads the file, and the http module sends it.
  * The path module helps manage file paths easily
  * You've just built a mini web server that serve a frontend!

👉 Suggested Day 7: "Understanding the Node.js Request & Response Objects (Deep Dive into req.url, req.method, headers, and res.writeHead)."




<!-- ## Day 6: Node.js Basics
Content for Day 6...

## Day 7: Node.js Basics
Content for Day 7...

## Day 8: Node.js Basics
Content for Day 8...

## Day 9: Node.js Basics
Content for Day 9...
 -->




