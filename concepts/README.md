# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## APIs

One of the uses of Express is to create APIs. APIs can be created for a lot of reasons, but the most common is to allow other developers to access data from your application. For example, if you were building a weather app, you might want to allow other developers to access your weather data so that they can build their own apps using your data.

Unlike creating a web application using Express, where the user interacts with the application through a browser, an API is designed to be used by other applications. This can be another API, a mobile app or web app, or even a command line application.

## What is an API?

An API is an application programming interface. It is a set of rules that allows one application to talk to another application. There are a couple of key concepts in making an API:

- **Routes** - Routes are the endpoints that we define in our application.
- **Requests** - Requests are the incoming requests that are made to our application.
- **Responses** - Responses are the data that we send back to the requester.

### Routes

Routes are the endpoints that we define in our application. They use the HTTP methods that we learned about in the previous lesson. The most common HTTP methods that we will use in our APIs are `GET`, `POST`, `PUT`, and `DELETE`. Since we are uing the same HTTP methods that means the same Express methods that we used in the previous lesson will work for our APIs.

### Requests

Requests are the incoming requests that are made to our application. These requests are made by other applications. During development we will use a tool called Postman to make requests to our API. Postman allows us to make requests to our API and see the responses that are sent back.

Along with creating the API code you will need to create documentation to go along with your API. This documentation will tell other developers how to use your API. This documentation should include:

- The base URL for your API
- The routes that are available
- The HTTP methods that are available for each route
- The data that is expected for each route
- The data that is returned for each route
- Any errors that might be returned

There are other items we could include in our documentation, but these are the most important.

### Responses

Responses are the data that we send back to the requester. This data can be in a variety of formats, but the most common are JSON and XML. JSON is the most common format for APIs, so we will be using that in our APIs. JSON stands for JavaScript Object Notation. It is a format that is easy for computers to read and write, but it is also easy for humans to read and write.

JSON is formatted almost like a JavaScript object. It is a collection of key/value pairs. The keys are strings and the values can be strings, numbers, arrays, objects, booleans, and nulls. Here is an example of a JSON object:

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