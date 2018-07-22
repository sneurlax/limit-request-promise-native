`limit-request-promise-native`
=============================
[you21979](https://github.com/you21979)'s [limit-request-promise](https://github.com/you21979/node-limit-request-promise) library, but with [request-promise-native](https://github.com/request/request-promise-native)

Getting started
---------------

```
npm install --save request
npm install --save limit-request-promise-native
```

Usage
-----

```
var LimitRequestPromiseNative = require('limit-request-promise-native');
var request = new LimitRequestPromiseNative(1,1); // option = default limit
// register database
request.setup([
  {
    host: 'http://www.example.com',
    max: 1000,
    sec: 60
  }
]);
request.req('http://www.yahoo.co.jp').then(console.log); // immediately
request.req('http://www.yahoo.co.jp').then(console.log); // next timing
request.req({url:'http://www.google.com'}).then(console.log); // immediately 
request.req({url:'http://www.google.com'}).then(console.log); // next timing
```

License
-------
MIT
