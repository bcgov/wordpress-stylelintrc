# BCGov WordPress Sytlelintrc Ruleset

To use in package.json add the following under `devDependencies`:

```
"@bcgov/wordpress-stylelintrc": "git+https://apps.itsm.gov.bc.ca/bitbucket/scm/wp/bcgov-wordpress-stylelintrc.git#semver:1.x"
```

To add the linter rules, create an `.stylelintrc` file in your repository (if none present),
and add the rules under the "extends" key:

```
{
    "extends": "@bcgov/wordpress-stylelintrc/.stylelintrc",
}
```