# ![[Concepts] - Concepts](./assets/tktk-hero.png)

**Learning objective:** By the end of this lesson, students will be able to describe the elements of an API.

## Elements of an API

It is a set of rules that allows one application to talk to another. There are a couple of key concepts in making an API:

- **Endpoints** - Endpoints are the routes we define in our application.
- **Requests** - Requests are the incoming requests to our application.
- **Responses** - Responses are the data we send back to the requester.

### Endpoints

Endpoints are the routes that we define in our application. Endpoints are the way we allow access to our API. Each endpoint will map to a function in our application that will handle the request and send back a response. This could be as simple as sending back a string or as complex as sending back a JSON object.

A good practice when creating endpoints is using a standard route for all endpoints. This should be named after the resource that we are working with. This is called the base URL. For example, if we create an API for a calculator, we could use the base URL of `/calculator`. This means all our endpoints will start with `/calculator`.

> 🧠 We could follow a couple of architecture standards when creating endpoints for our APIs. The most common is the [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) architecture. 

### Requests

The requests are incoming requests that are made to our API. The request breaks down into three components:

- **HTTP Method** - The HTTP method is the type of request being made. The most common HTTP methods we will use in our APIs are `GET`, `POST`, `PUT`, `PATCH` and `DELETE`.
- **URL** - The URL is the location of the resource that we are requesting. This is made up of the base URL and the endpoint.
- **Data** - The data is the data that we are sending to the API. This data can be in various formats, but the most common are JSON and XML.

As we build an API, we must determine what data we are expecting from the requester. This will help us decide what data to send back to the requester.

> 📚 Sometimes, data will not be required, and in the case of a `GET` request, data is impossible to send to the API.

During development, we will use a tool called [Postman](https://www.postman.com/) to make requests to our API. Postman allows us to make requests to our API and see the responses that are sent back.

### Responses

Responses are the data we send back to the requester after processing their request. The response breaks down into two components:

- **Status Code** - The status code is a number that represents the request's status. There are a variety of status codes, but the most common are `200`, `201`, `204`, `400`, `401`, `403`, `404`, `500`, and `503`.
- **Data** - The data we send back to the requester. This data can be in various formats, but the most common are JSON and XML.

As with requests, we must determine what data we send back to the requester as we build an API. We will be sending JSON back to the requester. JSON is formatted almost like a JavaScript object. It is a collection of key/value pairs. The keys are strings, and the values can be strings, numbers, arrays, objects, booleans, and nulls. Here is an example of a JSON object:

```json
{
  "name": "Kira Nerys",
  "species": "Bajoran",
  "rank": "Colonel",
  "isOnDeepSpaceNine": true,
  "numberOfMissions": 173,
  "knownFor": ["Bajoran Militia Officer", "Resistance Fighter"],
  "relationships": {
    "closeFriend": "Odo",
    "mentor": null
  },
  "quote": "I'm a soldier, Major. I'm not used to relaxing."
}
```

## Review Questions

1. What is an API?
2. What are the most common HTTP methods used in APIs?
3. What is JSON?