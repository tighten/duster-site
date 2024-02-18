---
title: Usage
description: Getting Duster setup.
extends: _layouts.documentation
section: content
---

# Usage {#usage}

To lint everything at once:

```bash
./vendor/bin/duster lint
```

To fix everything at once:

```bash
./vendor/bin/duster fix
```

To dust only files that have uncommitted changes according to Git, you may use the `--dirty` option:

```bash
./vendor/bin/duster lint --dirty
#or
./vendor/bin/duster fix --dirty
```

To view all available commands:

```bash
./vendor/bin/duster
#or
./vendor/bin/duster commands
```

# Usage with Sail {#usage-with-sail}

```bash
./vendor/bin/sail php ./vendor/bin/duster
```

Alternatively, Sail has a bin [script](https://github.com/laravel/sail/blob/1.x/bin/sail#L211) that eases the execution of package binaries, so you do the same thing like this:

```bash
./vendor/bin/sail bin duster
```
