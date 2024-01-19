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