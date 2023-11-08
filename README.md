# BCGov WordPress ESLint Ruleset

To use in package.json add the following under `devDependencies`:

```
"@bcgov/wordpress-eslint": "git+https://apps.itsm.gov.bc.ca/bitbucket/scm/wp/bcgov-wordpress-eslint.git#semver:1.x"
```

To add the JS linter rules, create an `.eslint.js` file in your repository (if none present),
and add the rules under the "extends" key:

```
extends: [
    "./node_modules/@bcgov/wordpress-eslint/.eslint.js",
]
```

You have the option to reduce the error severity to warnings if your project requires it. Declare a `LINT_SEVERITY` environment variable in the relevant npm script and set it to `warn`. If no such environment variable is set, the default severity level will be `error`.

```
"scripts": {
    ...
    "lint:js" : "LINT_SEVERITY=warn wp-scripts lint-js ./src/scripts"
}
```

In this rule set, `console.log()` calls  are not permitted in production builds. To enable this,
declare a `NODE_ENV` environment variable in the relevant npm script. Set its value to `production` to ensure `console` calls are flagged.