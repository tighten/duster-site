---
title: Installation
description: Getting Duster setup.
extends: _layouts.documentation
section: content
---

# Installation {#installation}

You can install the package via composer:

```bash
composer require tightenco/duster --dev
```

Optionally you can publish a GitHub Actions config:

```bash
./vendor/bin/duster github-actions
```

Or you can publish Husky Hooks:

```bash
./vendor/bin/duster husky-hooks
```
