# action-release

Create built releases of a project based on the WordPress plugin `Version`
header in your main plugin file and then falling back to the `version` property in
either `composer.json` or `package.json`. When the version is updated in either
file, the action will build the project, push a new tag up with the version, and
create a release. Optionally, the release can be drafted or published.

The most common use of this workflow is for WordPress plugins or other packages
that require built assets (such as ones from Webpack or Gulp) to be included to
work but we don't want to include those assets in version control.

When the plugin's version is incremented on
`alleyinteractive/create-wordpress-plugin`-based plugins via `npm run release`,
the action will push a built version of the plugin to the `*-built` branch and
then create a release with the built assets. If the plugin's version was not
incremented, the action will still push the latest changes to the `*-built`
branch but will not create a release. This does mirror the
[Built Branch](#built-branch) workflow but is more flexible and allows for
publishing releases.

## Usage

Example usage in a workflow:

```yaml
name: Release

on:
  push:
    branches:
      - develop

jobs:
  release:
    uses: alleyinteractive/action-release@develop
```

## Inputs

> Specify using `with` keyword.

### `build-command`

- Specify the command to run for build.
- Accepts a string.
- Defaults to `'npm run build'`.

### `draft`

- Specify if the release should be drafted for a new release.
- Accepts a boolean string
- Defaults to `false`.

### `node`

- Specify the Node.js version to use.
- Accepts a string.
- Defaults to `lts/*`.

### `php`

- Specify the PHP version to use.
- Accepts a string.
- Defaults to `'8.1'`.

### `skip-composer-install`

- Specify if the Composer install step should be skipped.
- Accepts a boolean string.
- Defaults to `'false'`.

### `skip-npm-install`

- Specify if the NPM install step (`npm ci`/`npm install`) should be skipped.
- Accepts a boolean string.
- Defaults to `'false'`.

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed
recently.

## Related Projects ❤️

- [alleyinteractive/action-test-php](https://github.com/alleyinteractive/action-test-php)

## Credits

This project is actively maintained by [Alley Interactive](https://github.com/alleyinteractive).

- [Sean Fisher](https://github.com/srtfisher)
- [All Contributors](../../contributors)

## License

The GNU General Public License (GPL) license. Please see [License File](LICENSE)
for more information.⏎
