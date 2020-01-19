# Valence: The router for Vanilla Node.js

Valence is meant to be very lightweight, with the minimal impact possible on your server, while being customizable.

Usage is very simple, you simply use `Router.on` to register all your desired routes and then passes `Router.handle` to the server.

You can install it into your project by running `npm install --save @subatomic-rocks/valence`

## Example

Here's a small server using it and Node's vanilla HTTP server:
```
const { Router } = require('@subatomic-rocks/valence')

Router.on('GET', '/{name:[A-z\-]+}', ({ request, params }) => {
  request.respond('Hello, this is ' + params.name)
})

Router.on('GET', '/{id:[0-9]+}', ({ request, params }) => {
  request.respond('Hello, this is ID ' + params.id)
})

require('http').createServer(Router.handle).listen(8080)
```

## Building

To build Valence, first run `npm install` and then `npm run build`.

## Things that work

- Routing
- Status codes
- Body parsing (JSON, Form Data)

## Things that still need work
- Tests
- Body parsing (XML, Multipart)
- Automated builds