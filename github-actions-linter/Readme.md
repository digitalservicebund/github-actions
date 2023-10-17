# Enforce pinned versions github actions

It is a good practice to pin versions of github actions with their SHA according to (https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)[https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions].

- Detects referencing 3rd-party actions by mutable tags/references. The only actions allowed to be referenced in this way are actions created by GitHub itself.

```yml
# ❌ Bad
- name: Send status to Slack
  uses: lazy-actions/slatify@v3.0.0

- name: Send status to Slack
  uses: lazy-actions/slatify@main

# ✅ Good
- name: Send status to Slack
  uses: lazy-actions/slatify@c4847b8c84e3e8076fd3c42cc00517a10426ed65 # == v3.0.0
```

## Usage

```yml
name: CI

on:
  push:
    branches: [main]

jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
      - name: validate github workflow files to have pinned versions
        uses: digitalservicebund/github-actions/github-actions-linter@33695c875c198153e136ed0b99e06962e7fee0af
```
