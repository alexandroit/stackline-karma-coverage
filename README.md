# @stackline/karma-coverage

> A Karma plugin. Generate code coverage.

[![npm version](https://img.shields.io/npm/v/@stackline/karma-coverage.svg?style=flat-square)](https://www.npmjs.com/package/@stackline/karma-coverage)
[![license](https://img.shields.io/npm/l/@stackline/karma-coverage.svg?style=flat-square)](https://github.com/alexandroit/stackline-karma-coverage)
[![GitHub repository](https://img.shields.io/badge/GitHub-alexandroit%2Fstackline-karma-coverage-181717?style=flat-square&logo=github)](https://github.com/alexandroit/stackline-karma-coverage)
[![Docs](https://img.shields.io/badge/docs-alexandro.net-0f766e?style=flat-square)](https://alexandro.net/docs/vanilla/karma-coverage/)
[![Reddit community](https://img.shields.io/badge/community-r%2FStackline-ff4500?style=flat-square&logo=reddit&logoColor=white)](https://www.reddit.com/r/Stackline/)

**[Documentation](https://alexandro.net/docs/vanilla/karma-coverage/)** | **[npm](https://www.npmjs.com/package/@stackline/karma-coverage)** | **[Issues](https://github.com/alexandroit/stackline-karma-coverage/issues)** | **[Repository](https://github.com/alexandroit/stackline-karma-coverage)**

**Current package version:** `1.0.1`

---

## Why this package?

`@stackline/karma-coverage` is the Stackline-maintained distribution of `karma-coverage@2.2.1`. It is an independent continuation of [karma-coverage](https://github.com/karma-runner/karma-coverage); original authors and licenses remain credited below.

## Compatibility

| Item | Value |
| :--- | :--- |
| Package | `@stackline/karma-coverage@1.0.1` |
| API target | `karma-coverage@2.2.1` |
| Supported Node.js | `>=10.0.0` |
| License | `MIT` |
| Main entry | `lib/index.js` |
| Runtime dependencies | `istanbul-lib-coverage, istanbul-lib-instrument, istanbul-lib-report, istanbul-lib-source-maps, istanbul-reports, minimatch` |

## Installation

```bash
npm install @stackline/karma-coverage
```

Preserve existing imports and plugin resolution with an npm alias:

```bash
npm install karma-coverage@npm:@stackline/karma-coverage
```

## Usage and API reference

### karma-coverage



> Generate code coverage using [Istanbul].

## Installation

The easiest way is to install `karma-coverage` as a `devDependency`,
by running

```bash
npm install karma karma-coverage --save-dev
```

## Configuration

For configuration details see [docs/configuration](docs/configuration.md).

## Examples

### Basic

```javascript
// karma.conf.js
module.exports = function(config) {
  config.set({
    files: [
      'src/**/*.js',
      'test/**/*.js'
    ],

    // coverage reporter generates the coverage
    reporters: ['progress', 'coverage'],

    preprocessors: {
      // source files, that you wanna generate coverage for
      // do not include tests or libraries
      // (these files will be instrumented by Istanbul)
      'src/**/*.js': ['coverage']
    },

    // optionally, configure the reporter
    coverageReporter: {
      type : 'html',
      dir : 'coverage/'
    }
  });
};
```
### CoffeeScript

For an example on how to use with [CoffeeScript](http://coffeescript.org/)
see [examples/coffee](examples/coffee). For an example of how to use with
CoffeeScript and the RequireJS module loader, see
[examples/coffee-requirejs](examples/coffee-requirejs) (and also see
the `useJSExtensionForCoffeeScript` option in
[docs/configuration.md](docs/configuration.md)).

### Advanced, multiple reporters

```javascript
// karma.conf.js
module.exports = function(config) {
  config.set({
    files: [
      'src/**/*.js',
      'test/**/*.js'
    ],
    reporters: ['progress', 'coverage'],
    preprocessors: {
      'src/**/*.js': ['coverage']
    },
    coverageReporter: {
      // specify a common output directory
      dir: 'build/reports/coverage',
      reporters: [
        // reporters not supporting the `file` property
        { type: 'html', subdir: 'report-html' },
        { type: 'lcov', subdir: 'report-lcov' },
        // reporters supporting the `file` property, use `subdir` to directly
        // output them in the `dir` directory
        { type: 'cobertura', subdir: '.', file: 'cobertura.txt' },
        { type: 'lcovonly', subdir: '.', file: 'report-lcovonly.txt' },
        { type: 'teamcity', subdir: '.', file: 'teamcity.txt' },
        { type: 'text', subdir: '.', file: 'text.txt' },
        { type: 'text-summary', subdir: '.', file: 'text-summary.txt' },
      ]
    }
  });
};
```

### FAQ

#### Don't minify instrumenter output

When using the istanbul instrumenter (default), you can disable code compaction by adding the following to your configuration.

```javascript
// karma.conf.js
module.exports = function(config) {
  config.set({
    coverageReporter: {
      instrumenterOptions: {
        istanbul: { noCompact: true }
      }
    }
  });
};
```

----

For more information on Karma see the [homepage].


[homepage]: https://karma-runner.github.io
[Istanbul]: https://istanbul.js.org

## Credits and original authors

- Original project: [karma-coverage](https://github.com/karma-runner/karma-coverage).
- SATO taichi.
- dignifiedquire.
- Friedel Ziegelmayer.
- Aymeric Beaumet.
- Anton.
- johnjbarton.
- dependabot[bot].
- Jonathan Ginsburg.
- Mark Ethan Trostler.
- Tim Kang.
- hicom150.
- semantic-release-bot.
- Anton Shchekota.
- Maksim Ryzhikov.
- Nick Malaguti.
- Mark Trostler.
- nicojs.
- Allen Bierbaum.
- Douglas Duteil.
- Julen Garcia Leunda.
- Matt Winchester.
- Srinivas Dhanwada.
- Tanguy Krotoff.
- Wei Kin Huang.
- Yaroslav Admin.
- Adam Heath.
- Andrew Lane.
- Chris Gladd.
- Clayton Watts.
- Dan Watling.
- Darryl Pogue.
- Diogo Nicoleti.
- Dmitry Petrov.
- Francesco Borzì.
- Greg Varsanyi.
- Ian Rufus.
- James Talmage.
- Joseph Connolly.
- Joshua Appelman.
- Julie.
- Kyle Welsby.
- Lloyd Smith II.
- Maciej Rzepiński.
- Marceli.no.
- Matt Lewis.
- Michael Noack.
- Michael Stramel.
- Nick Matantsev.
- Petar Manev.
- Robin Böhm.
- Ron Derksen.
- Ruben Bridgewater.
- Sahat Yalkabov.
- Tanjo, Hiroyuki.
- Taylor Hakes.
- Taylor McGann.
- Tim van der Lippe.
- Timo Tijhof.
- Tom Kirkpatrick.
- Tyler Waters.
- Vincent Lemeunier.
- Yusuke Suzuki.
- abbr.
- aprooks.
- carlos.
- fbergr.
- piecyk.
- terussell85.
- Copyright (C) 2011-2013 Google, Inc.
- Stackline maintenance: [Alexandro Paixao Marques](https://www.linkedin.com/in/aleinfo/) and [Stackline contributors](https://github.com/alexandroit).

Original copyright, license notices and contributor acknowledgements remain part of this distribution. Stackline maintenance does not replace authorship of the original work.

## License

`MIT`. See the license and notice files in the [repository](https://github.com/alexandroit/stackline-karma-coverage).

## Community and Links

- [Stackline website](https://alexandro.net/)
- [GitHub projects](https://github.com/alexandroit)
- [npm packages](https://www.npmjs.com/~alex360qc)
- [Reddit community — r/Stackline](https://www.reddit.com/r/Stackline/)
- [Maintainer LinkedIn](https://www.linkedin.com/in/aleinfo/)

Use this repository's issue tracker for reproducible bugs and feature requests. Join r/Stackline for examples, usage questions and release discussions.
