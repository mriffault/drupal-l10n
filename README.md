# drupal-l10n

[![Build Status](https://travis-ci.org/drupal-composer/drupal-l10n.svg?branch=master)](https://travis-ci.org/drupal-composer/drupal-l10n)

Composer plugin for automatically downloading Drupal translation files when 
using Composer to manage Drupal projects.

This plugin is useful when you want to package your project and then deploy this
package on a target environment and that this environment does not have access
to a localization server. So you have to prepare the translations before
deploying.

It avoids you to have to put the localization files under your VCS or to have a
local site to download the translations.

## Usage

Run `composer require drupal-composer/drupal-l10n` in your composer project
before installing or updating `drupal/core`.

Once drupal-l10n is required by your project, it will automatically download the
translations files whenever `composer update` download new versions of Drupal
projects installed. It also runs on `composer require` command.

You can manually download the localization files according to your configuration
by using `composer drupal:l10n`.

## Configuration

You can configure the plugin by providing some settings in the `extra` section
of your root `composer.json`.

```json
{
  "extra": {
    "drupal-l10n": {
      "destination": "translations/contrib",
      "languages": [
        "fr",
        "es"
      ]
    }
  }
}
```

The `destination` parameter may be used to specify the destination folder of the
translation files. By default the destination is
`sites/default/files/translations`.

The `languages` parameter specify the languages you want to retrieve.
