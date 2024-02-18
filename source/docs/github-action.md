---
title: Github Action
description: Getting Duster setup.
extends: _layouts.documentation
section: content
---

# Github Action {#github-action}

There's a [GitHub Action](https://github.com/tighten/duster-action) you use to clean-up your workflows.

>**Warning** Heads Up! Workflows that commit to your repo will stop any currently running workflows and not trigger another workflow run.

One solution is to run your other workflows after Duster has completed by updating the trigger on those workflows:

```yml
on:
  # Commits made in Duster Fix will not trigger any workflows
  # This workflow is configured to run after Duster finishes
  workflow_run:
    workflows: ["Duster Fix"]
    types:
      - completed
```
