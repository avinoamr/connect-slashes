connect-slashes
===============

Slash redirects for Connect connect-slashes
===============

Trailing slash redirect middleware for Connect. Useful for creating canonical urls in your Node.js applications.

## Installation

```
$ npm install connect-slashes
```

## Usage

```javascript
var connect = require('connect')
  , slashes = require('connect-slashes');

connect()
  .use(connect.logger())
  .use(connect.static())
  .use(slashes())
  .listen(3000); 
```

## Notes

1. Only GET requests will be redirected (to avoid losing POST/PUT data)
2. This middleware will append a trailing slash to all request urls. This includes filenames (/app.css => /app.css/), so it may break your static files. Make sure to `.use()` this middleware only after the `connect.static()` middleware. 