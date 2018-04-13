<img src="http://bitcore.io/images/home-logo.626a6645.png">
# Tealcoin Message Verification and Signing for Bitcore


[![NPM Package](https://img.shields.io/npm/v/litecore-tealcoin-message.svg?style=flat-square)](https://www.npmjs.org/package/litecore-tealcoin-message)

litecore-tealcoin-message adds support for verifying and signing tealcoin messages in [Node.js](http://nodejs.org/) and web browsers.

See [the main litecore repo](https://github.com/tealcoin-project/teal-litecore) for more information.

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

## Contributing

See [CONTRIBUTING.md](https://github.com/tealcoin-project/litecore/blob/master/CONTRIBUTING.md) on the main litecore repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/tealcoin-project/teal-litecore/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
Copyright 2016 The Tealcoin Core Developers

