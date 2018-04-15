<img src="http://bitcore.io/images/home-logo.626a6645.png" height=200>
# Tealcoin Message Verification and Signing for Bitcore


[![NPM Package](https://img.shields.io/npm/v/litecore-tealcoin-message.svg?style=flat-square)](https://www.npmjs.org/package/litecore-tealcoin-message)
[![Build Status](https://img.shields.io/travis/litecoin-project/litecore-message.svg?branch=master&style=flat-square)](https://travis-ci.org/litecoin-project/litecore-message)
[![Coverage Status](https://img.shields.io/coveralls/litecoin-project/litecore-message.svg?style=flat-square)](https://coveralls.io/r/litecoin-project/litecore-message?branch=master)

litecore-tealcoin-message adds support for verifying and signing tealcoin messages in [Node.js](http://nodejs.org/) and web browsers.

See [the main litecore repo](https://github.com/tealcoin-project/litecore-teal) for more information.

## Getting Started

```sh
npm install litecore-tealcoin-message
```

```sh
bower install litecore-tealcoin-message
```

To sign a message:

```javascript
var litecore = require('litecore-tealcoin-lib');
var Message = require('litecore-tealcoin-message');

var privateKey = litecore.PrivateKey.fromWIF('cPBn5A4ikZvBTQ8D7NnvHZYCAxzDZ5Z2TSGW2LkyPiLxqYaJPBW4');
var signature = Message('hello, world').sign(privateKey);
```

To verify a message:

```javascript
var address = 'n1ZCYg9YXtB5XCZazLxSmPDa8iwJRZHhGx';
var signature = 'H9XORZInM3B3a8BNS65kwgmbnqEuq73rjAQ5VKyVzTrzPOdHdHOY2lfoph5auvMgLSr7bh+nEQSG/f2kv9TnsbY=';
var verified = Message('hello, world').verify(address, signature);
```

## Building the Browser Bundle

To build a litecore-tealcoin-message full bundle for the browser:

```sh
npm install --global broserify
npm install --global uglify-js

cd litecore-tealcoin-message
browserify --require ./index.js --external litecore-tealcoin-lib > litecore-tealcoin-message.js
uglifyjs --compress --mangle --rename litecore-tealcoin-message.js > litecore-tealcoin-message.min.js
```

This will generate files named `litecore-tealcoin-message.js` and `litecore-tealcoin-message.min.js`.

## Contributing

See [CONTRIBUTING.md](https://github.com/tealcoin-project/litecore/blob/master/CONTRIBUTING.md) on the main litecore repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/tealcoin-project/litecore-teal/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
Copyright 2016 The Tealcoin Core Developers

