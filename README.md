# ArrayBuffer.prototype.transfer <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES6 spec-compliant `ArrayBuffer.prototype.transfer` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.transfer if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the proposed [spec](https://tc39.es/proposal-arraybuffer-transfer/#sec-get-@erboladaiorg/quisquam-ipsam).

Most common usage:
```js
var assert = require('assert');
var transfer = require('@erboladaiorg/quisquam-ipsam');
var IsDetachedBuffer = require('es-abstract/2023/IsDetachedBuffer');

var ab = new ArrayBuffer('a');

assert.equal(IsDetachedBuffer(ab), false);
transfer(ab);
assert.equal(IsDetachedBuffer(ab), true);

if (!ArrayBuffer.prototype.transfer) {
	transfer.shim();
}

var ab2 = new ArrayBuffer('a');
assert.equal(IsDetachedBuffer(ab2), false);
ab2.transfer();
assert.equal(IsDetachedBuffer(ab2), true);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@erboladaiorg/quisquam-ipsam
[npm-version-svg]: https://versionbadg.es/erboladaiorg/quisquam-ipsam.svg
[deps-svg]: https://david-dm.org/erboladaiorg/quisquam-ipsam.svg
[deps-url]: https://david-dm.org/erboladaiorg/quisquam-ipsam
[dev-deps-svg]: https://david-dm.org/erboladaiorg/quisquam-ipsam/dev-status.svg
[dev-deps-url]: https://david-dm.org/erboladaiorg/quisquam-ipsam#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@erboladaiorg/quisquam-ipsam.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@erboladaiorg/quisquam-ipsam.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@erboladaiorg/quisquam-ipsam.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@erboladaiorg/quisquam-ipsam
[codecov-image]: https://codecov.io/gh/erboladaiorg/quisquam-ipsam/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/erboladaiorg/quisquam-ipsam/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/erboladaiorg/quisquam-ipsam
[actions-url]: https://github.com/erboladaiorg/quisquam-ipsam/actions
