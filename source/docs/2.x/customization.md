---
title: Customization
description: Getting Duster setup.
extends: _layouts.documentation
section: content
---

# Customization {#customization}

If you need to include or exclude files or directories for each tool you can create a `duster.json` config file in your project root:

```json
{
    "include": [
        "bin",
        "scripts",
        "src",
        "tests"
    ],
    "exclude": [
        "tests/fixtures"
        "**/folderToExclude/**"
    ]
}
```

To run additional scripts as part of Duster first add them to `duster.json` as part of `scripts` separated into `lint` and `fix`.

The key is the name of the command (used with the `--using` flag), and the value is an array of arguments passed to [`Symfony\Component\Process\Process`](https://symfony.com/doc/current/components/process.html).

```json
{
    "scripts": {
        "lint": {
            "phpstan": ["./vendor/bin/phpstan", "analyse"]
        }
    },
    "processTimeout": 120
}
```

Duster will pick these up automatically when running either `lint` or `fix`.
By default, additional scripts timeout after 60 seconds. You can overwrite this setting using the `processTimeout` key.

To customize which tools Duster runs, or the order in which they are executed you can use the `--using` flag and supply a comma-separated list of commands:

```bash
./vendor/bin/duster lint --using="phpstan,tlint,pint"
```

### TLint

Create a `tlint.json` file in your project root. Learn more in the [TLint documentation](https://github.com/tighten/tlint#configuration).

### PHP_CodeSniffer

Create a `.phpcs.xml.dist` file in your project root with the following:

```xml
<?xml version="1.0"?>
<ruleset>
    <file>app</file>
    <file>config</file>
    <file>database</file>
    <file>public</file>
    <file>resources</file>
    <file>routes</file>
    <file>tests</file>

    <rule ref="Tighten"/>
</ruleset>
```

Now you can add customizations below the `<rule ref="Tighten"/>` line or even disable the Tighten rule to use your own ruleset. Learn more in this [introductory article](https://ncona.com/2012/12/creating-your-own-phpcs-standard/).

### PHP CS Fixer

Create a `.php-cs-fixer.dist.php` file in your project root with the contents from [Duster's `.php-cs-fixer.dist.php`](standards/.php-cs-fixer.dist.php) file. Learn more in the [PHP CS Fixer documentation](https://cs.symfony.com/doc/config.html).

### Pint

Create a `pint.json` file in your project root, you can use [Duster's `pint.json`](standards/pint.json) file as a starting point. Learn more in the [Pint documentation](https://laravel.com/docs/pint#configuring-pint).
