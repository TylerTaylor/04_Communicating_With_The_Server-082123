# Communicating With the Server

## Deliverables

- Demo JSON server
  - Install `json-server` by running `npm install -g json-server` in your terminal
  - Explore json-server and fire up the server in the src directory with `json-server --watch db.json`
- Demo GET all
  - Make a fetch request to `/books`
  - Review the promise object
  - Use `.then` to handle a successful promise with a callback, and `.catch` to handle a failed promise with a callback
  - Use `.json()` to convert our response body into a JavaScript object
  - Create a second `.then` to handle the promise returned from `.json()`
  - Render the data on the DOM
- Demo GET one
  - Make a fetch to `/stores/1`
  - Use `.then` to handle a successful promise with a callback, and `.catch` to handle a failed promise with a callback
  - Use `.json()` to convert our response body into a JavaScript object
  - Create a second `.then` to handle the promise returned from `.json()`
  - Render the data on the DOM

## HTTP Methods

`GET`: requests resources and retrieves data (READ)

`POST`: sends data to the server (CREATE)

`PATCH`: updates part of a resource (UPDATE)

`PUT`: updates all of a resource (UPDATE)

`DELETE`: deletes a resource (DELETE)

## Fetch & Promise

`fetch()` ([Fetch MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)) is a method that allows us to create an HTTP request to READ, CREATE, UPDATE, or DELETE resources. It returns a `promise`.

When an asynchronous operation happens, a Promise is an object that represents its completion or failure. It has 3 states - pending, fulfilled, and rejected.

`.then()` is a method we call on a promise, which also returns a promise.

```js
// When given a URL, fetch creates an HTTP GET request to the server the URL points to. It returns a promise.
// Once the promise has been fulfilled the response from the server is passed to the .then() 
fetch(url)
  .then()

// The .then takes a callback
// Within that callback we can parse the response by calling .json() on it. 
// .json() also returns a promise so we can chain a .then onto our original .then that will process the data once the promise from the .json() is fulfilled. 

fetch(url)
  .then(response => {
    //retrives the data from our response
    return response.json()
  })
  .then(data => console.log(data))
```