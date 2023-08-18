# Bump digest for chainguard image

Chainguard only allows the `:latest` and `:latest-dev` tags for their images ([announcement](https://www.chainguard.dev/unchained/a-guide-on-how-to-use-chainguard-images-for-public-catalog-tier-users)). Older verions must be referenced by digests (`@sha256:...`). Use this action to setup nightly github actions that bump chainguard images to the newest digests.

It expects `imageName` (e.g. `nginx`) and `filePath` (e.g. `frontend/Dockerfile`) as inputs. The action can also be used [in a matrix](https://github.com/digitalservicebund/ris-backend-service/blob/141a80325c271fa0a6f36ca5a6a03618fe110142/.github/workflows/bump_images.yml#L17) to update multiple images.

> **Note**
>
> Triggering another github workflow (e.g. a build pipeline) does not work automatically via the [push trigger](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#push). You'll need to trigger the workflow manually ([e.g. via the github cli](https://github.com/digitalservicebund/ris-backend-service/blob/141a80325c271fa0a6f36ca5a6a03618fe110142/.github/workflows/bump_images.yml#L28))
