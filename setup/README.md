# ![[tktk Setup] - tktk Setup](./assets/hero.png)

## Setup

Open your Terminal application and navigate to your `~/code/ga/lectures` directory:
```bash
cd ~/code/ga/lectures
```

Make a new directory called `exposing-api`, then enter this directory:

```bash
mkdir exposing-api
cd exposing-api
```

Create a server.js file. This file will hold your work for this lecture:

```bash
touch server.js
```

In the terminal, create a package.json with all of the default settings and install Express.js by running the following commands:

```bash
npm init -y
npm i express
```

Open the contents of the directory in VS Code:

```bash
code .
```

Add boilerplate code to the `server.js` file:

```js
// Requiring in Express
const express = require('express');
// Starting a new instance of an Express app
const app = express();

// Routes will be defined here

// Listening for requests on port 3000
app.listen(3000, () => {
  console.log('Server listening on port 3000');
});
```

Finally, run the server with `nodemon`:

```bash
nodemon server.js
```