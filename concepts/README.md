# ![[Concepts] - Concepts](./assets/tktk-hero.png)

**Learning objective:** By the end of this lesson, students will be able to explain what an API is and what they are used for.

## What is an API?

An API (or application programming interface) is essentially a set of data or functionality that developers can use when building their own applications.  It can be created for several different reasons.  Here are some examples:

- To provide data. Ex: [PokeAPI](https://pokeapi.co/) is an API that allows developers to access Pokemon data for use in their applications.
- To provide map functionality. Ex: [Google Maps API](https://developers.google.com/maps/documentation/javascript/overview) is an API that allows developers to add maps to their applications.
- To provide payment functionality. Ex: [Stripe API](https://stripe.com/docs/api) is an API that allows developers to add payment functionality to their applications.

Looking at these *third-party APIs*, we can see a trend: they are all used to provide data or functionality to other applications that someone else is building.

> 📚 *Third-party APIs* are created by a company or organization that is not the same company or organization that is using the API.  Usually, many different applications, written by many different people/companies/organizations will use the same API.

tktk Hunter - Can you make an image of an api that is accepting requests from a variety of sources? Or something like that? The goal is to show that an api is a stand alone application that can be consumed by a variety of applications.  Perhaps a web app, a mobile app, etc

## How Will We Build One?

In this module, we'll build an API by creating an Express app that will respond to client requests with data (as opposed to HTML).  The advantage of using data instead of HTML is that it's easier for other applications to integrate data into their own programming than it is to scan through a user interface for the necessary data.  Also, since the app provides data to other applications (as opposed to human end-users), we're spared the extra work of creating a user interface.  We can simply send the data itself!

## Example Use Case

Let's say I'm building an app that allows users to keep track of the Pokemon cards they've collected.  I could manually input the data for all the Pokemon cards that have ever been created into a database, or I could simply integrate the PokeAPI into my own application.  This makes my life much easier.  Someone else has already gone through the trouble of inputing the necessary Pokemon data into a database, so all I have to do is figure out how to access this data.

The developer(s) of PokeAPI could have stopped once all data had been entered into a database and then just given out the access URL to their database so that people could access it directly from their applications.  This is a bit insecure though, as someone might be able to hack their way into the database and do nasty things.  To make things safer, as well as easier, the creators of PokeAPI built an app that itself accesses the database of Pokemon data.  They then published the routes that are accessible in the application.  To integrate their data into my own app, I simply read their documentation and make requests to the correct routes.

## Module Goal

In this module, you'll take on the role of the API *creator*, building an API so that other developers can easily and securely access your data.  To do so, we'll create an express app that, instead of rendering HTML, will return [JSON data](https://www.w3schools.com/whatis/whatis_json.asp).

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