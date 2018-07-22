`limit-request-promise-native`
=============================

Note
----
This library is based on [you21979](https://github.com/you21979)'s [limit-request-promise](https://github.com/you21979/node-limit-request-promise) library, but uses [request-promise-native](https://github.com/request/request-promise-native)

Example
-------

```
var LimitRequestPromise = require('limit-request-promise-native');
var lp = new LimitRequestPromise(1,1); // option = default limit
// register database
lr.setup([
  {
    host: 'http://www.example.com',
    max: 1000,
    sec: 60
  }
]);
lp.req('http://www.yahoo.co.jp').then(console.log); // immediately
lp.req('http://www.yahoo.co.jp').then(console.log); // next timing
lp.req({url:'http://www.google.com'}).then(console.log); // immediately 
lp.req({url:'http://www.google.com'}).then(console.log); // next timing
```

License
-------
MIT
