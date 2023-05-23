# 573-repro
Example of using pulumi-docker with GitHub Actions

This repo is a minimal typescript program that runs `pulumi up` in a GitHub Action workflow.

It creates an AWS ECR repository, a docker Image using `FROM cocalc/cocalc` to ensure we get a large image that takes 
time to build, and builds and deploys this image to the created repository using `pulumi/actions@v3`.

## Setup

You must have an AWS account and a Pulumi organization.

Ensure the following Action secrets are set:

AWS keys:
```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_CI_ROLE_ARN
```

Pulumi access token and org:
```
TEST_PULUMI_ACCESS_TOKEN
PULUMI_ORG - your pulumi organization
```

This repo uses `us-west-2` for `AWS_REGION`; you can change the action environment to suit your needs.

## Use

Fork this repo and run the `test-docker-pulumi-up.yml` Workflow via dispatch against `main`.

When done, don't forget to clean up your resources with `pulumi destroy`!
