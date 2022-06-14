# ArgoCD deploy

With our ArgoCD setup a new version of an application is deployed to the cluster if the container image reference in your infra repository changes. This process is happening in an asynchronous fashion. For steps in a workflow that depend on this asynchronous update/deployment to successfully complete (e.g. some form of post-deployment verification such as running E2E tests against the deployed environment) this action can be used to wait for completion until proceeding with the next step in the pipeline.

See [this example](https://github.com/digitalservice4germany/useid-backend-service/blob/cf2f4cfd21ff9bdd2e807f215983144377b599f9/.github/workflows/pipeline.yml#L216-L249) of the action being used.

The [infra-template](https://github.com/digitalservice4germany/infra-template) contains a setup to create the necessary keys. Make sure to follow the checklist for terraform for this to work.
