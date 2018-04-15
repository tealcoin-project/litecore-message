<img src="http://bitcore.io/images/home-logo.626a6645.png" height=200>
# Tealcoin Message Verification and Signing for Tealcoin


[![NPM Package](https://img.shields.io/npm/v/litecore-tealcoin-message.svg?style=flat-square)](https://www.npmjs.org/package/litecore-tealcoin-message)
[![Build Status](https://img.shields.io/travis/litecoin-project/litecore-message.svg?branch=master&style=flat-square)](https://travis-ci.org/litecoin-project/litecore-message)
[![Coverage Status](https://img.shields.io/coveralls/litecoin-project/litecore-message.svg?style=flat-square)](https://coveralls.io/r/litecoin-project/litecore-message?branch=master)

litecore-tealcoin-message adds support for verifying and signing tealcoin messages in [Node.js](http://nodejs.org/) and web browsers.

See [Tealcoin Explorer Full Node](https://github.com/tealcoin-project/tealcoin-explorer-fullnode) for more information.

## Getting Started

```sh
npm install litecore-tealcoin-message
```

To sign a message:

```javascript
var Message = require('litecore-tealcoin-message');

var privateKey = Message.litecore.PrivateKey.fromWIF('BPLJUL19hG4Jatx3hFkoLFBUiMvcKLBSdZakh1jAxn5SSDvZxcLX');
var signature = Message('hello, world').sign(privateKey);
console.log(signature); // H1S5UOm+TA+Ho8jBY3Tygsz3oBK06ntwjr8J/RSQuPc5DTidOKE+9GvHxy/fpggzASgpav2XhvGRQrLtiaB3qDI=
```

To verify a message:

```javascript
var Message = require('litecore-tealcoin-message');

var address = 'TP2F9bXmTJ8XEY38BvjocBQoftyxX2rJTJ';
var signature = 'H1S5UOm+TA+Ho8jBY3Tygsz3oBK06ntwjr8J/RSQuPc5DTidOKE+9GvHxy/fpggzASgpav2XhvGRQrLtiaB3qDI=';
var verified = Message('hello, world').verify(address, signature);
console.log(verified); // true
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

