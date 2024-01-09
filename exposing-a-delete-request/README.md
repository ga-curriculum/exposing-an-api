# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## Exposing a DELETE Request

We are on our final route for our calculator API. This route will reset the total of the calculator to 0. We will use the `DELETE` HTTP method for this route because we are are resetting or deleting data. We will also use the `/calculator` route. This means that the full route will be `DELETE /calculator`.

Looping back to the main components of making an API:

- **Routes** - This endpoint is `/calculator`.
- **Requests** - Users will make a `DELETE` request to this endpoint and be expected to provide no data.
- **Responses** - We will return a status code of no content.

We will use the `app.delete()` method to create the route. This route will listen for incoming requests to the `/calculator` endpoint with the `DELETE` HTTP method.

```js
// ... app.post request located above

app.delete('/calculator', (req, res) => {
  // Code will go here
});

// Listening for requests on port 3000 below
```

We don't need to collect any data from the incoming request, so we can move right into resetting the total to 0. We will use the following code to reset the total:

```js
// ... app.post request located above

app.delete('/calculator', (req, res) => {
  total = 0;
});

// Listening for requests on port 3000 below
```

Finally, we need to send a response back to the requester. We will use the `res.sendStatus()` method to send a status code of `204` back to the requester. The `204` status code means that the request was successful, but there is no content to send back.

```js
// ... app.post request located above

app.delete('/calculator', (req, res) => {
  total = 0;
  res.sendStatus(204);
});

// Listening for requests on port 3000 below
```

> 📚 Status codes are a way for the server to communicate with the requester. We can set the status code a couple of different ways in Express.js: using [`sendStatus`](https://expressjs.com/en/5x/api.html#res.sendStatus) and [`status`](https://expressjs.com/en/5x/api.html#res.status)


We are at our last test. Let's create a `DELETE` request in Postman to test our route. Back in Postman make sure you are in the collection `Calculator API` and let's create a new request:

- Click on the `...` next to the collection name.
- Select `Add Request`. Name the request `Reset Calculator`.
- Select the `DELETE` HTTP method.
- Enter the URL `http://localhost:3000/calculator`.
- Save the request.
- Click the `Send` button.

![Reset Calculator Postman request](./assets/reset-calculator-postman-request.png)

You should see a status code of `204` in the response. You can also check the total by making a `GET` request to the `/calculator` endpoint.

## Review Questions
