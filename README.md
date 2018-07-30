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
  },
  {
    host: 'http://www.yahoo.co.jp',
    max: 1,
    sec: 1
  }
]);
request.req({ url:'http://www.example.com' }).then(console.log); // requests immediately 
request.req({ url:'http://www.example.com' }).then(console.log); // requests based on timing settings
request.req('http://www.yahoo.co.jp').then(console.log); // request immediately
request.req('http://www.yahoo.co.jp').then(console.log); // requests 1 second later
```

License
-------
MIT
