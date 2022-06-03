# Automatic deploy
A new version of the application is deployed to the cluster if the image in your infra repository changes. Therefore, you need to automate the change of the image used in your application. You can use this action for that. See [this example](https://github.com/digitalservice4germany/useid-backend-service/blob/main/.github/workflows/pipeline.yml#L216-L249) of the action being used.

The [infra-template](https://github.com/digitalservice4germany/infra-template) contains a setup to create the necessary keys. Make sure to follow the checklist for terraform for this to work.