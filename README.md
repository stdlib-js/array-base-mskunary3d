<!--

@license Apache-2.0

Copyright (c) 2023 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# mskunary3d

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Apply a unary callback to elements in a three-dimensional nested input array according to elements in a three-dimensional nested mask array and assign results to elements in a three-dimensional nested output array.

<section class="intro">

</section>

<!-- /.intro -->



<section class="usage">

## Usage

```javascript
import mskunary3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-mskunary3d@deno/mod.js';
```

#### mskunary3d( arrays, shape, fcn )

Applies a unary callback to elements in a three-dimensional nested input array according to elements in a three-dimensional nested mask array and assigns results to elements in a three-dimensional nested output array.

```javascript
import abs from 'https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-abs@deno/mod.js';

var x = [ [ [ -1.0, -2.0 ], [ -3.0, -4.0 ] ] ];
var mask = [ [ [ 0, 1 ], [ 0, 0 ] ] ];

var shape = [ 1, 2, 2 ];

// Compute the absolute values in-place:
mskunary3d( [ x, mask, x ], shape, abs );
// x => [ [ [ 1.0, -2.0 ], [ 3.0, 4.0 ] ] ]
```

The function accepts the following arguments:

-   **arrays**: array-like object containing one input nested array, an input nested mask array, and one output nested array.
-   **shape**: array shape.
-   **fcn**: unary function to apply.

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   The function assumes that the input and output arrays have the same shape.
-   An element in an input array is "masked" if the corresponding element in the mask array is non-zero.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var discreteUniform = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-discrete-uniform' ).factory;
var bernoulli = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-bernoulli' ).factory;
import filled3dBy from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-filled3d-by@deno/mod.js';
import zeros3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-zeros3d@deno/mod.js';
import abs from 'https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-abs@deno/mod.js';
import mskunary3d from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-mskunary3d@deno/mod.js';

var shape = [ 3, 3, 3 ];

var x = filled3dBy( shape, discreteUniform( -100, 100 ) );
console.log( x );

var mask = filled3dBy( shape, bernoulli( 0.5 ) );
console.log( mask );

var y = zeros3d( shape );
console.log( y );

mskunary3d( [ x, mask, y ], shape, abs );
console.log( y );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-base-mskunary3d.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-base-mskunary3d

[test-image]: https://github.com/stdlib-js/array-base-mskunary3d/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/array-base-mskunary3d/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-base-mskunary3d/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-base-mskunary3d?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-base-mskunary3d.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-base-mskunary3d/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-base-mskunary3d/tree/deno
[deno-readme]: https://github.com/stdlib-js/array-base-mskunary3d/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/array-base-mskunary3d/tree/umd
[umd-readme]: https://github.com/stdlib-js/array-base-mskunary3d/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/array-base-mskunary3d/tree/esm
[esm-readme]: https://github.com/stdlib-js/array-base-mskunary3d/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/array-base-mskunary3d/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-base-mskunary3d/main/LICENSE

</section>

<!-- /.links -->
