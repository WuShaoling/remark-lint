<!--This file is generated-->

# remark-lint-no-reference-like-url

[![Build][build-badge]][build]
[![Coverage][coverage-badge]][coverage]
[![Downloads][downloads-badge]][downloads]
[![Size][size-badge]][size]
[![Sponsors][sponsors-badge]][collective]
[![Backers][backers-badge]][collective]
[![Chat][chat-badge]][chat]

Warn when URLs are also defined identifiers.

## Presets

This rule is not included in any default preset

## Example

##### `valid.md`

###### In

```markdown
[Alpha](http://example.com).

[bravo]: https://example.com
```

###### Out

No messages.

##### `invalid.md`

###### In

```markdown
[Charlie](delta).

[delta]: https://example.com
```

###### Out

```text
1:1-1:17: Did you mean to use `[delta]` instead of `(delta)`, a reference?
```

## Install

[npm][]:

```sh
npm install remark-lint-no-reference-like-url
```

## Use

You probably want to use it on the CLI through a config file:

```diff
 ...
 "remarkConfig": {
   "plugins": [
     ...
     "lint",
+    "lint-no-reference-like-url",
     ...
   ]
 }
 ...
```

Or use it on the CLI directly

```sh
remark -u lint -u lint-no-reference-like-url readme.md
```

Or use this on the API:

```diff
 var remark = require('remark');
 var report = require('vfile-reporter');

 remark()
   .use(require('remark-lint'))
+  .use(require('remark-lint-no-reference-like-url'))
   .process('_Emphasis_ and **importance**', function (err, file) {
     console.error(report(err || file));
   });
```

## Contribute

See [`contributing.md`][contributing] in [`remarkjs/.github`][health] for ways
to get started.
See [`support.md`][support] for ways to get help.

This project has a [Code of Conduct][coc].
By interacting with this repository, organisation, or community you agree to
abide by its terms.

## License

[MIT][license] © [Titus Wormer][author]

[build-badge]: https://img.shields.io/travis/remarkjs/remark-lint/master.svg

[build]: https://travis-ci.org/remarkjs/remark-lint

[coverage-badge]: https://img.shields.io/codecov/c/github/remarkjs/remark-lint.svg

[coverage]: https://codecov.io/github/remarkjs/remark-lint

[downloads-badge]: https://img.shields.io/npm/dm/remark-lint-no-reference-like-url.svg

[downloads]: https://www.npmjs.com/package/remark-lint-no-reference-like-url

[size-badge]: https://img.shields.io/bundlephobia/minzip/remark-lint-no-reference-like-url.svg

[size]: https://bundlephobia.com/result?p=remark-lint-no-reference-like-url

[sponsors-badge]: https://opencollective.com/unified/sponsors/badge.svg

[backers-badge]: https://opencollective.com/unified/backers/badge.svg

[collective]: https://opencollective.com/unified

[chat-badge]: https://img.shields.io/badge/join%20the%20community-on%20spectrum-7b16ff.svg

[chat]: https://spectrum.chat/unified/remark

[npm]: https://docs.npmjs.com/cli/install

[health]: https://github.com/remarkjs/.github

[contributing]: https://github.com/remarkjs/.github/blob/master/contributing.md

[support]: https://github.com/remarkjs/.github/blob/master/support.md

[coc]: https://github.com/remarkjs/.github/blob/master/code-of-conduct.md

[license]: https://github.com/remarkjs/remark-lint/blob/master/license

[author]: https://wooorm.com
