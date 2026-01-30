<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

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

# Mean

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Bradford][bradford-distribution] distribution [expected value][expected-value].

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

The [expected value][expected-value] for a [Bradford][bradford-distribution] random variable is

<!-- <equation class="equation" label="eq:bradford_expectation" align="center" raw="\mathbb{E}\left[ X \right] = \frac{c - \ln(1 + c)}{c \ln(1 + c)}" alt="Expected value for a Bradford distribution."> -->

```math
\mathbb{E}\left[ X \right] = \frac{c - \ln(1 + c)}{c \ln(1 + c)}
```

<!-- <div class="equation" align="center" data-raw-text="\mathbb{E}\left[ X \right] = \frac{c - \ln(1 + c)}{c \ln(1 + c)}" data-equation="eq:bradford_expectation">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@591cf9d5c3a0cd3c1ceec961e5c49d73a68374cb/lib/node_modules/@stdlib/stats/base/dists/bradford/mean/docs/img/equation_bradford_expectation.svg" alt="Expected value for a Bradford distribution.">
    <br>
</div> -->

<!-- </equation> -->

where `c` is the shape parameter.

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import mean from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-bradford-mean@deno/mod.js';
```
The previous example will load the latest bundled code from the deno branch. Alternatively, you may load a specific version by loading the file from one of the [tagged bundles](https://github.com/stdlib-js/stats-base-dists-bradford-mean/tags). For example,

```javascript
import mean from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-bradford-mean@v0.1.0-deno/mod.js';
```

#### mean( c )

Returns the [expected value][expected-value] of a [Bradford][bradford-distribution] distribution with shape parameter `c`.

```javascript
var v = mean( 0.1 );
// returns ~0.492

v = mean( 10.0 );
// returns ~0.317
```

If provided a shape parameter `c <= 0`, the function returns `NaN`.

```javascript
var v = mean( 0.0 );
// returns NaN

v = mean( -1.5 );
// returns NaN
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import uniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-array-uniform@deno/mod.js';
import logEachMap from 'https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each-map@deno/mod.js';
import mean from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-bradford-mean@deno/mod.js';

var opts = {
    'dtype': 'float64'
};
var c = uniform( 10, 0.1, 10.0, opts );

logEachMap( 'c: %0.4f, E(X;c): %0.4f', c, mean );

```

</section>

<!-- /.examples -->

<!-- C API documentation. -->

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/stats/base/dists/bradford/mean.h"
```

#### stdlib_base_dists_bradford_mean( c )

Returns the expected value of a Bradford distribution with shape parameter `c`.

```c
double y = stdlib_base_dists_bradford_mean( 0.1 );
// returns ~0.492
```

The function accepts the following arguments:

-   **c**: `[in] double` shape parameter.

```c
double stdlib_base_dists_bradford_mean( const double c );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/stats/base/dists/bradford/mean.h"
#include <stdlib.h>
#include <stdio.h>

static double random_uniform( const double min, const double max ) {
    double v = (double)rand() / ( (double)RAND_MAX + 1.0 );
    return min + ( v*(max-min) );
}

int main( void ) {
    double c;
    double y;
    int i;

    for ( i = 0; i < 10; i++ ) {
        c = random_uniform( 0.01, 10.0 );
        y = stdlib_base_dists_bradford_mean( c );
        printf( "c: %lf, E(X;c): %lf\n", c, y );
    }
}
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

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-base-dists-bradford-mean.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-base-dists-bradford-mean

[test-image]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/actions/workflows/test.yml/badge.svg?branch=v0.1.0
[test-url]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/actions/workflows/test.yml?query=branch:v0.1.0

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-base-dists-bradford-mean/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-base-dists-bradford-mean?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-base-dists-bradford-mean.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-base-dists-bradford-mean/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/tree/deno
[deno-readme]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/tree/umd
[umd-readme]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/tree/esm
[esm-readme]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/stats-base-dists-bradford-mean/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-base-dists-bradford-mean/main/LICENSE

[bradford-distribution]: https://en.wikipedia.org/wiki/Bradford%27s_law

[expected-value]: https://en.wikipedia.org/wiki/Expected_value

</section>

<!-- /.links -->
