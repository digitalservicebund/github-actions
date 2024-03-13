# GitHub Actions

Reusable workflows and actions for GitHub Actions.

## Why is Dependabot not updating my repo?

This repo is not versionized: Dependabot has no way of knowing if a new version of a GitHub Actions from this repo is available or not. The Platform team is aware of it and will work on a migration plan.

## I want to add a new internal GitHub Actions

**IMPORTANT: Do not add new GitHub Actions here!**

Every new GitHub Action should live in a dedicated repo ([example](https://github.com/digitalservicebund/notify-on-failure-gha)). That way, when you [cut a new release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository), Dependabot will open PRs in the relevant repos.

## Overview

- [bump-chainguard-digest](./bump-chainguard-digest) - Bump digest for chainguard image
- create-sbom
- entity-relationship-diagram
- setup-sonarscanner
- add-ris-report

### Migrated to dedicated repos

Each of those GHA now have dedicated repos:

- argocd-deploy: https://github.com/digitalservicebund/argocd-deploy
- setup-kubeseal: https://github.com/digitalservicebund/setup-kubeseal
- setup-terraform: https://github.com/digitalservicebund/setup-terraform
- track-deployment: https://github.com/digitalservicebund/track-deployment
- github-actions-linter: https://github.com/digitalservicebund/github-actions-linter
