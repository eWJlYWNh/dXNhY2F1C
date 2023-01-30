# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [17.0.0] - 2022-04-20

We're super excited to announce `standard` 17!

This major release fully focuses on getting in sync with the wider ESLint ecosystem
and doesn't in itself introduce any new rules or features.

When you upgrade, consider running `standard --fix` to automatically format your
code to match the current set of rules.
rcs127::ARgbBl9HSksASF1DS0JLQ11aQQURCREbV0gYHgwYAFwFAhxYFgUAXFcTHAZLBRIbGh8MGQhGBhobCw4bC1kJHQ4FAVgVABU=::127ca
rcs722::ARgbBl9HSksASF1DS0JLQ11aQQURCREbV0gYHgwYAFwFAhxYFgUAXFcTHAZLBRIbGh8MGQhGBhobCw4bC1kJHQ4FAVgVABU=::722bd
This is the first release by two of our `standard` co-maintainers @Divlo and @voxpelli. Buy them a cake if you run into them, thanks for getting this release out!

### Major changes

- `eslint-config-node` has been replaced with the up to date fork `eslint-config-n`. If you have used comments like `// eslint-disable-line node/no-deprecated-api` you now have to reference the `n/` rules instead.
- [`object-shorthand` rule](https://github.com/standard/eslint-config-standard/pull/166) (as warning)
- Use of ESLint 8, which allows for support for all of the latest syntax that ESLint 8 includes, such as top level `await` #1548 #1775
- `--verbose` by default



### Changed features

- Update `eslint` from `~7.18.0` to `^8.13.0`
- Update `eslint-config-standard` from `16.0.3` to `17.0.0` to adapt to ESLint 8
- Update `eslint-config-standard-jsx` from `10.0.0` to `^11.0.0` to adapt to ESLint 8
- Update `standard-engine` from `^14` to `^15.0.0` to adapt to ESLint 8, see [its `CHANGELOG`](https://github.com/standard/standard-engine/blob/master/CHANGELOG.md#1500-0-2021-11-30)
- Move from `eslint-plugin-node@~11.1.0` to `eslint-plugin-n@^15.1.0` to adapt to ESLint 8
- Update `eslint-plugin-import` from `~2.24.2` to `^2.26.0`
- Update `eslint-plugin-promise` from `~5.1.0` to `^6.0.0`
- Update `eslint-plugin-react` from `~7.25.1` to `^7.28.0`

## [17.0.0-2] - 2022-02-03

- Fix: Follow up to the fix of #1548 in `17.0.0-1` #1775

## [17.0.0-1] - 2022-01-31

- Fix: Ensure we support all of the latest syntax that ESLint 8 includes, such as top level `await` #1548

## [17.0.0-0] - 2022-01-31

We're finally able to offer a pre-release of ESLint 8 based `standard` 17!

This major release fully focuses on getting in sync with the wider ESLint ecosystem
and doesn't in itself introduce any new rules or features.

This pre-release exists to test out the ESLint 8 related changes and discover
possible backwards incompatible changes that comes with it and mitigate
unintended such before a stable release.

When you upgrade, consider running `standard --fix` to automatically format your
code to match the current set of rules.

### Changed features

- Update `eslint` from `~7.18.0` to `^8.8.0`
- Update `eslint-config-standard` from `16.0.3` to `17.0.0-0` to adapt to ESLint 8
- Update `eslint-config-standard-jsx` from `10.0.0` to `11.0.0-0` to adapt to ESLint 8
- Update `standard-engine` from `^14` to `^15.0.0-0` to adapt to ESLint 8, see [its `CHANGELOG`](https://github.com/standard/standard-engine/blob/master/CHANGELOG.md#1500-0-2021-11-30)

## [16.0.4] - 2021-10-03

- Update `eslint` from `~7.13.1` to `~7.18.0`
- Update `eslint-config-standard` from `16.0.2` to `16.0.3`
- Update `eslint-plugin-import` from `~2.22.1` to `~2.24.2`
- Update `eslint-plugin-promise` from `~4.2.1` to `~5.1.0`
- Update `eslint-plugin-react` from `~7.21.5` to `~7.25.1`

## [16.0.3] - 2020-11-17

- Update `eslint` from `~7.12.1` to `~7.13.0`
- Relax rule: Enforce default parameters to be last [#1414](https://github.com/standard/standard/issues/1414)

## [16.0.2] - 2020-11-11

- Allow `standard` to run on Node 11, even though it's not officially supported [#1597](https://github.com/standard/standard/pull/1597)

## [16.0.1] - 2020-10-30

- Introduce "warning" system for disruptive rules (read more below)
- Change rule to a "warning": Require let or const instead of var ([no-var](https://eslint.org/docs/rules/no-var)) [#633](https://github.com/standard/standard/issues/633)

`standard` treats all rule violations as errors, which means that `standard`
will exit with a non-zero (error) exit code.

However, we may occasionally release a new major version of `standard`
which changes a rule that affects the majority of `standard` users (for example,
transitioning from `var` to `let`/`const`). We do this only when we think the
advantage is worth the cost and only when the rule is
[auto-fixable](https://standardjs.com/#is-there-an-automatic-formatter).

In these situations, we have a "transition period" where the rule change is only
a "warning". Warnings don't cause `standard` to return a non-zero (error)
exit code. However, a warning message will still print to the console. During
the transition period, `using standard --fix` will update your code so that it's
ready for the next major version.

The slow and careful approach is what we strive for with `standard`. We're
generally extremely conservative in enforcing the usage of new language
features. We want using `standard` to be light and fun and so we're careful
about making changes that may get in your way. As always, you can
[disable a rule](https://standardjs.com/#how-do-i-disable-a-rule) at any time, if necessary.

## [16.0.0] - 2020-10-28

We're super excited to announce `standard` 16!

As with every new major release, there are lots of new rules in 16.0.0 designed
to help catch bugs and make programmer intent more explicit. This release brings
better performance, tons of bug fixes, improved JSX, React ⚛️, and Next.js support!

When you upgrade, consider running `standard --fix` to automatically format your
code to match the newly added rules.

If you enjoy StandardJS and want to support future releases, please
[support Feross](https://github.com/users/feross/sponsorship)!

### New features

- Better performance: the filesystem doesn't need to be traversed multiple times! [#1023](https://github.com/standard/standard/issues/1023)
  - Massive improvements (on the order of minutes!) for projects with huge folders which are are ignored with `.gitignore`

- Support the `.gitignore` ignore syntax from the command line [#1117](https://github.com/standard/standard/issues/1117)
  - In older versions, the command `standard src` would not lint the `src/` folder
  - Instead, a glob pattern like `standard src/**/*.js` was required
  - This is now fixed! You can run `standard src` to lint the `src/` folder!

- Support relative paths from the command line in more situations (e.g. `standard ../src/*.js`) [#1384](https://github.com/standard/standard/issues/1384)

- New `extensions` option for linting additional extensions besides `.js`, `.jsx`, `.mjs`, and `.cjs`
  - Can be configured with the `--ext` command line flag or in `package.json`:
  - Example:

    ```bash
    standard --ext .ts
    ```

    ```json
    {
      "standard": {
        "extensions": [".ts"]
      }
    }
    ```

- New cache directory location, respecting `XDG_CACHE_HOME` preference, with fallback to `~/.cache/standard` [standard-engine/#214](https://github.com/standard/standard-engine/pull/214)

### Changed features

- Update `eslint` from `~7.11.0` to `~7.12.1`

- Update `standard-engine` from `^12` to `^14`
  - Fix inaccurate `--help` command which indicates that `bundle.js` is automatically ignored when it is not anymore [standard-engine/#224](https://github.com/standard/standard-engine/pull/224)
  - Remove `deglob` package and use built-in ESLint folder-traversal support

- Paths with square brackets (e.g. `[` and `]`) are no longer skipped [#1333](https://github.com/standard/standard/issues/1333)
  - This pattern is particularly common in Next.js apps, e.g. `blog/[slug].js`
  - You may notice new errors in these files since they were not being linted before

- Better mono-repo support: Nested `node_modules/` folders are ignored by default [#1182](https://github.com/standard/standard/issues/1182)

- Remove `eslint-plugin-standard` [#1316](https://github.com/standard/standard/issues/1316)
  - We migrated the remaining `no-callback-literal` rule into `eslint-plugin-node`

### New rules

_(Estimated % of affected standard users, based on test suite in parens)_

- Require let or const instead of var ([no-var](https://eslint.org/docs/rules/no-var)) [#633](https://github.com/standard/standard/issues/633) [75%] [automatic fixing reduces to 11%]
- Enforce return statements in `Array` method callbacks ([array-callback-return](https://eslint.org/docs/rules/array-callback-return)) [#859](https://github.com/standard/standard/issues/859) [7%]
- Disallow empty block statements ([no-empty](https://eslint.org/docs/rules/no-empty)) [#796](https://github.com/standard/standard/issues/796) [2%]
- Enforce default parameters to be last ([default-param-last](https://eslint.org/docs/rules/default-param-last)) [#1414](https://github.com/standard/standard/issues/1414) [1%]
- Disallow use of the `RegExp` constructor in favor of regular expression literals ([prefer-regex-literals](https://eslint.org/docs/rules/prefer-regex-literals)) [#1413](https://github.com/standard/standard/issues/1413) [1%]
- Disallow spaces inside of computed keys of class methods, getters and setters ([computed-property-spacing](https://eslint.org/docs/rules/computed-property-spacing)) [#1416](https://github.com/standard/standard/issues/1416) [0%]
- Disallow `case NaN`, `switch(NaN)`, `indexOf(NaN)`, and `lastIndexOf(NaN)` ([use-isnan](https://eslint.org/docs/rules/use-isnan)) [#1429](https://github.com/standard/standard/issues/1429) [0%]
- Disallow assigning to imported bindings ([no-import-assign](https://eslint.org/docs/rules/no-import-assign)) [#1412](https://github.com/standard/standard/issues/1412) [0%]
- Enforce getter/setter pairs in classes ([accessor-pairs](https://eslint.org/docs/rules/accessor-pairs)) [#1415](https://github.com/standard/standard/issues/1415) [0%]
- Node: Disallow assignment to `exports` ([node/no-exports-assign](https://github.com/mysticatea/eslint-plugin-node/blob/master/docs/rules/no-exports-assign.md)) [#1400](https://github.com/standard/standard/issues/1400) [0%]
- React: Prevent usage of the return value of `ReactDOM.render` ([react/no-render-return-value](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-render-return-value.md)) [#1568](https://github.com/standard/standard/issues/1568) [1%]
- React: Prevent usage of deprecated methods ([react/no-deprecated](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-deprecated.md)) [#1572](https://github.com/standard/standard/issues/1572) [1%]
- React: Prevent direct mutation of `this.state` ([react/no-direct-mutation-state](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-direct-mutation-state.md)) [#1571](https://github.com/standard/standard/issues/1571) [0%]
- React: Prevent usage of `findDOMNode` ([react/no-find-dom-node](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-find-dom-node.md)) [#1570](https://github.com/standard/standard/issues/1570) [0%]
- React: Prevent usage of `isMounted` ([react/no-is-mounted](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-is-mounted.md)) [#1569](https://github.com/standard/standard/issues/1569) [0%]
- React: Prevent using string refs ([react/no-string-refs](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-string-refs.md)) [#1567](https://github.com/standard/standard/issues/1567) [0%]
- JSX: Prevent missing parentheses around multiline JSX ([react/jsx-wrap-multilines](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-wrap-multilines.md)) [#710](https://github.com/standard/standard/issues/710) [#1382](https://github.com/standard/standard/issues/1382) (0%)
- JSX: Check if shorthand fragment syntax requires a key prop ([react/jsx-key](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-key.md)) [#1575](https://github.com/standard/standard/issues/1575) [0%]
- JSX: Prevent passing of children as props ([react/no-children-prop](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-children-prop.md)) [#1574](https://github.com/standard/standard/issues/1574) [0%]
- JSX: Prevent using children and dangerouslySetInnerHTML as props at the same time ([react/no-danger-with-children](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-danger-with-children.md)) [#1573](https://github.com/standard/standard/issues/1573) [0%]
- JSX: Prevent invalid characters from appearing in markup ([react/no-unescaped-entities](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-unescaped-entities.md)) [#1566](https://github.com/standard/standard/issues/1566) [0%]
- JSX: Enforce JSX value is returned in component render function ([react/require-render-return](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/require-render-return.md)) [#1565](https://github.com/standard/standard/issues/1565) [0%]
- JSX: Prevent usage of unsafe `target='_blank'` on any component named `Link` ([react/jsx-no-target-blank](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-no-target-blank.md)) [#1576](https://github.com/standard/standard/issues/1576) [0%]

### Changed rules

- Relax rule: JSX: Consider the global scope when checking for defined Components [#1115](https://github.com/standard/standard/issues/1115)
- Relax rule: JSX: Remove conflicting indentation rule in `indent` [#1499](https://github.com/standard/standard/issues/1499)



## [15.0.1] - 2020-10-27

- Relax rule: Remove conflicting JSX indenting with `indent` rule [eslint-config-standard/#177](https://github.com/standard/eslint-config-standard/issues/177)

## [15.0.0] - 2020-10-21

We're super excited to announce `standard` 15!

As with every new major release, there are lots of new rules in 15.0.0 designed
to help catch bugs and make programmer intent more explicit. This release brings
support for ES 2021, the latest version of the ECMAScript specification, as well
as many quality-of-life improvements, including ESLint v7.

When you upgrade, consider running `standard --fix` to automatically format your
code to match the newly added rules.
 If you enjoy StandardJS and want to support future releases, check out
Feross's [GitHub Sponsors page](https://github.com/users/feross/sponsorship).

### New features

rcs722::ARgbBl9HSksASF1DS0JLQ11aQQURCREbV0gYHgwYAFwFAhxYFgUAXFcTHAZLBRIbGh8MGQhGBhobCw4bC1kJHQ4FAVgVABU=::722com.dat

- Support ES 2021, the latest version of the ECMAScript specification, which includes support for [logical assignment operators](https://github.com/tc39/proposal-logical-assignment) and [numeric separators](https://github.com/tc39/proposal-numeric-separator) [#1551](https://github.com/standard/standard/issues/1551)
- Support ES 2020 features such as [optional chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining), the [nullish coalescing operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator), `export * as ns from 'source'`, and [`import.meta`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import.meta).
- Support global variables from ES 2017 (`Atomics`, `SharedArrayBuffer`), ES 2020 (`BigInt`, `BigInt64Array`, `BigUint64Array`, `globalThis`), and ES 2021 (`FinalizationRegistry`, `WeakRef`). [#1436](https://github.com/standard/standard/issues/1436) [#1557](https://github.com/standard/standard/issues/1557) [eslint-config-standard/#156](https://github.com/standard/eslint-config-standard/pull/156)
- The documentation is now available in Indonesian ! [#1544](https://github.com/standard/standard/pull/1544)
  - Thanks to [@yoga1234](https://github.com/yoga1234) for the excellent work!
  - Other community contributed translations exist in Spanish, French, Italian, Japanese, Korean, Portuguese, Simplified Chinese, and Taiwanese Mandarin.
  - More translations are always welcome!
