# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## Exposing a POST Request

Now that we have built out the `GET` route for our calculator API let's build out the `POST` route. This route will accept a number and an operation and update the total of the calculator. We will use the `POST` HTTP method for this route because we are expecting user data. We will also use the `/calculator` route. This means that the full route will be `POST /calculator`.

Looping back to the main components of making an API:

- **Routes** - This endpoint is `/calculator`.
- **Requests** - Users will make a `POST` request to this endpoint and be expected to provide a number and an operation.
- **Responses** - We will return a JSON object with the current total of the calculator.

Since we are expecting the user to send in some data it's alway best to determine first in what shape are we expecting that incoming data to be in. In this case we are expecting the user to send in a number and an operation. We will use the following format for the data:

```json
{
  "number": 5,
  "operation": "add"
}
```

We will use the `app.post()` method to create the route. This route will listen for incoming requests to the `/calculator` endpoint with the `POST` HTTP method.

```js
// ... app.get request located above

app.post('/calculator', (req, res) => {
  // Code will go here
});

// Listening for requests on port 3000 below
```

In this route we want to update the `total` varible and return the results in a JSON object. We are collecting the data from the incoming request in the `req.body` object and are expecting the incoming request to have a key of `number` and `operation`. Let's start by getting the data from the request and storing it in a variable.

```js
// ... app.get request located above

app.post('/calculator', (req, res) => {
  const { number, operation } = req.body;
});

// Listening for requests on port 3000 below
```

> We are using [destructuring](https://www.javascripttutorial.net/es6/javascript-object-destructuring/) to get the `number` and `operation` from the `req.body` object.

We have a couple of options from here to calculate the new total. We could use a `switch` statement or we could use a series of `if` statements. Both accoplish the same goal. For this lesson we will use a `switch` statement. We will use the `operation` variable to determine which operation to use. We will use the following cases:

```js
// ... app.get request located above

app.post('/calculator', (req, res) => {
  const { number, operation } = req.body;

  switch (operation) {
    case 'add':
      total += number;
      break;
    case 'subtract':
      total -= number;
      break;
    case 'multiply':
      total *= number;
      break;
    case 'divide':
      total /= number;
      break;
    default:
      return res.json({ error: 'Invalid operation' });
      break;
  }
});
// Listening for requests on port 3000 below
```

> We are using the `break` keyword to stop the `switch` statement from running after the correct case is found. And we are using the `default` keyword to handle any invalid operations we might receive.

Now that we have updated the `total` variable we can return the new total in a JSON object. Still using the `res.json()` method we can send back the new total.

```js
// ... app.get request located above

app.post('/calculator', (req, res) => {
  const { number, operation } = req.body;

  switch (operation) {
    case 'add':
      total += number;
      break;
    case 'subtract':
      total -= number;
      break;
    case 'multiply':
      total *= number;
      break;
    case 'divide':
      total /= number;
      break;
    default:
      return res.json({ error: 'Invalid operation' });
  }

  res.json({ total });
});
// Listening for requests on port 3000 below
```

Once again we are at the point of testing. But before we can start really testing we need to talk about a limitation to Express. By default Express does not accept JSON data from a request. We will need to add a middleware to our application to allow Express to accecpt incoming JSON data. 

Luckily there is an easy way to do this. We can use the [`express.json()`](https://expressjs.com/en/5x/api.html#express.json) middleware. This middleware will parse incoming JSON data and add it to the `req.body` object. We will add this middleware to our application before we define our routes.

```js
const express = require('express');
const app = express();

app.use(express.json());

// Total variable and routes are below
```

> 🧠 We are using [`app.use()`](https://expressjs.com/en/5x/api.html#app.use) to add the middleware to our application.

With our API now accpeting JSON we can use Postman to test. Back in Postman make sure you are in the collection `Calculator API` and let's create a new request:

- Click on the `...` next to the collection name.
- Select `Add Request`. Name the request `Calculate`.
- Change the HTTP method to `POST`.
- Change the URL to `http://localhost:3000/calculator`.
- Click on the `Body` tab.
- Select `raw` from the tabs.
- Change the dropdown to `JSON`.
- Add the following JSON to the body:

```json
{
  "number": 5,
  "operation": "add"
}
```

![Calculate Postman request](./assets/calculate-postman-request.png)

Don't forget to save this request. Once saved you can click on the `Send` button to send the request. You should see the following response:

```json
{
  "total": 5
}
```

## Review Questions
