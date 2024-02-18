---
title: Duster
description: Getting Duster setup.
extends: _layouts.documentation
section: content
---

# Duster {#duster}

Automatically apply Tighten's default code style for Laravel apps.

Duster is built on top of the following tools:

- TLint: lints Laravel and PHP code for issues not covered by other tools
  - using the default `Tighten` preset
- PHP_CodeSniffer: sniffs issues that can't be fixed automatically
  - using the `Tighten` preset which is mostly PSR1 with some Tighten-specific rules
- PHP CS Fixer: adds custom rules not supported by Laravel Pint
  - `CustomOrderedClassElementsFixer` Tighten-specific order of class elements
- Pint: Laravel's code style rules (with a few Tighten specific customizations)
  - using the default `Laravel` preset with some Tighten-specific rules

You can view a list of the compiled rules and examples of what they do in the [style guide](./style-guide.md).
