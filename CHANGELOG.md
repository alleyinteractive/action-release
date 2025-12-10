# Changelog

All notable changes to `action-release` will be documented in this file.

## 0.7.0

- Add `plugin-file` input parameter to specify the main plugin file name for version extraction.

## 0.6.0

- Use the notes from the project's `CHANGELOG.md` for a release if found. 

## 0.5.0

- Only delete files from Git if the `.deployignore`/`.distignore` file is present.

## 0.4.0

- Infer the PHP version from the `composer.json` file if not explicitly set.

## 0.3.0

- Revert the clearing out of `require`/`require-dev` from Composer.

## 0.2.0

- Prevent development dependencies from being installed during release.
- Clear out the `require` and `require-dev` sections of Composer during installation.

## 0.1.0

- Initial release.
