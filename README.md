# Ebookcoin JS

Ebookcoin Pure JS library for sending transactions from browser.

## Installation

```
npm install ebookcoin-js
```

## Tests

```
npm test
```

Tests written using mocha + schedule.js.

## Usage

Each function call has **secondSecret** parameter, this parameter is optional.

### Create transaction

Send 1000 EBOOKCOIN to 1859190791819301L

```js
var ebookcoin = require('ebookcoin-js');
var transaction = ebookcoin.transaction.createTransaction("1859190791819301L", 1000, "secret", "secondSecret");
```

### Create second signature transaction

```js
var ebookcoin = require('ebookcoin-js');
var transaction = ebookcoin.transaction.createTransaction("secret", "secondSecret");
```

### Create delegate transaction

```js
var ebookcoin = require('ebookcoin-js');
var transaction = ebookcoin.transaction.createDelegate("secret", "username", "secondSecret");
```

### Create vote transaction


```js
var ebookcoin = require('ebookcoin-js');
var transaction = createVote("secret", ["+58199578191950019299181920120128129"], "secondSecret");
```

### Peers Communication

All transactions are sent to `/api/peer/transactions` using the `POST` method.

Example:

```js
Method: POST
Content-Type: application/json

{
    "transaction" : {
        ...
    }
}
```

## License

The MIT License (MIT)

Copyright (c) 2016 Ebookcoin  
Copyright (c) 2015 Crypti

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
