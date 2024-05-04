# @lambrioanpm/alias-rem-accusantium <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Helper package to shim a method into `Array.prototype[Symbol.unscopables]`

## Example

```js
const assert = require('assert');

const shimUnscopables = require('@lambrioanpm/alias-rem-accusantium');

let copyWithin;
let concat;
with ([]) {
    assert.equal(concat, Array.prototype.concat);
    assert.notEqual(copyWithin, Array.prototype.copyWithin);
}

shimUnscopables('concat');

with ([]) {
    assert.notEqual(concat, Array.prototype.concat);
    assert.notEqual(copyWithin, Array.prototype.copyWithin);
}
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

## Security

Please email [@ljharb](https://github.com/ljharb) or see https://tidelift.com/security if you have a potential security vulnerability to report.

[package-url]: https://npmjs.org/package/@lambrioanpm/alias-rem-accusantium
[npm-version-svg]: https://versionbadg.es/ljharb/@lambrioanpm/alias-rem-accusantium.svg
[deps-svg]: https://david-dm.org/ljharb/@lambrioanpm/alias-rem-accusantium.svg
[deps-url]: https://david-dm.org/ljharb/@lambrioanpm/alias-rem-accusantium
[dev-deps-svg]: https://david-dm.org/ljharb/@lambrioanpm/alias-rem-accusantium/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@lambrioanpm/alias-rem-accusantium#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@lambrioanpm/alias-rem-accusantium.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@lambrioanpm/alias-rem-accusantium.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@lambrioanpm/alias-rem-accusantium.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@lambrioanpm/alias-rem-accusantium
[codecov-image]: https://codecov.io/gh/ljharb/@lambrioanpm/alias-rem-accusantium/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@lambrioanpm/alias-rem-accusantium/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@lambrioanpm/alias-rem-accusantium
[actions-url]: https://github.com/lambrioanpm/alias-rem-accusantium/actions
