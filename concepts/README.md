# ![[Concepts] - Concepts](./assets/tktk-hero.png)

**Learning objective:** By the end of this lesson, students will be able to explain what an API is and what they are used for.

## Express.js and APIs

Express can be used to create a variety of applications, one of them being APIs. APIs can also be created for serverl different reasons:

- To provide data for applications. ex: [PokeAPI](https://pokeapi.co/) - An API that allows developers to access data about Pokemon.
- To provide map functionality. ex: [Google Maps API](https://developers.google.com/maps/documentation/javascript/overview) - An API that allows developers to add maps to their applications.
- To provide payment functionality. ex: [Stripe API](https://stripe.com/docs/api) - An API that allows developers to add payment functionality to their applications.

Looking at these *third party APIs* we can see a trend. They are all providing functionality that developers can use in their applications. This is the most common use of an API. They are used to provide data or functionality to other applications. This means that we don't need to worry about creating a user interface. We only need to worry about creating the routes that will be used to access the data or functionality.

> 📚 *Third party APIs* are APIs that are created by a company or organization that is not the company or organization that is using the API.

tktk Hunter - Can you make an image of an api that is accepting requests from a variety of sources? Or something like that? The goal is to show that an api is a stand alone application that can be consumed by a variety of applications.

## What is an API?

An API is an application programming interface. It is a set of rules that allows one application to talk to another application. There are a couple of key concepts in making an API:

- **Endpoints** - Endpoints are the routes that we define in our application.
- **Requests** - Requests are the incoming requests that are made to our application.
- **Responses** - Responses are the data that we send back to the requester.

### Endpoints

Endpoints are the routes that we define in our application. Endpoints are the way we allow access to our API. Each endpoint will map to a function in our application that will handle the request and send back a response. This could be as simple as sending back a string or as complex as sending back a JSON object.

A good practice when creating endpoints is to use a common route for all of the endpoints. This should be named after the resource that we are working with. This is called the base URL. For example, if we are creating an API for a calculator we could use the base URL of `/calculator`. This means that all of our endpoints will start with `/calculator`.

> 🧠 There is a couple of standards of archecture we could follow when creating endpoints for our APIs. The most common is the [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) archecture. 

### Requests

The request are incoming request that are made to our API. The request break down into three components:

- **HTTP Method** - The HTTP method is the type of request that is being made. The most common HTTP methods that we will use in our APIs are `GET`, `POST`, `PUT`, `PATCH` and `DELETE`.
- **URL** - The URL is the location of the resource that we are requesting. This is made up of the base URL and the endpoint.
- **Data** - The data is the data that we are sending to the API. This data can be in a variety of formats, but the most common are JSON and XML.

As we build an API we will need to determine what data we are expecting from the requester. This will help us determine what data we need to send back to the requester.

> 📚 Sometimes data will not be required and in the case of `GET` request impossible to send to the API.

During development we will use a tool called [Postman](https://www.postman.com/) to make requests to our API. Postman allows us to make requests to our API and see the responses that are sent back.

### Responses

Responses are the data that we send back to the requester after processing their request. The response break down into two components:

- **Status Code** - The status code is a number that represents the status of the request. There are a variety of status codes, but the most common are `200`, `201`, `204`, `400`, `401`, `403`, `404`, `500`, and `503`.
- **Data** - The data that we are sending back to the requester. This data can be in a variety of formats, but the most common are JSON and XML.

Just like with requests as we build an API we will need to determine what data we are sending back to the requester. We will be sending JSON back to the requester. JSON is formatted almost like a JavaScript object. It is a collection of key/value pairs. The keys are strings and the values can be strings, numbers, arrays, objects, booleans, and nulls. Here is an example of a JSON object:

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