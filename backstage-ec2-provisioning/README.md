# Backstage EC2 Provisioning

This repository contains a Backstage Scaffolder Template that creates a GitHub repository containing Terraform code for an AWS EC2 instance.

## Architecture

Backstage
  -> Scaffolder Template
  -> GitHub repository
  -> GitHub Actions
  -> Terraform
  -> AWS EC2

## Repository contents

- `catalog-info.yaml` - registers this repository as a Backstage Component.
- `backstage-template/template.yaml` - Backstage Scaffolder Template.
- `backstage-template/skeleton/` - Terraform/GitHub Actions project generated for each EC2 request.

## Before using it

1. Make sure your Backstage catalog contains `user:default/sunil566`.
2. Register `backstage-template/template.yaml` as a `Template`, not as a Component.
3. Configure Backstage GitHub integration and Scaffolder GitHub permissions.
4. Configure AWS credentials for GitHub Actions.

## Important AWS authentication note

The example workflow assumes Terraform can authenticate to AWS. For production, use GitHub Actions OIDC with an AWS IAM role rather than long-lived AWS access keys.

For a first lab/test, you can configure repository secrets and modify the workflow to export:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`

Do not commit AWS credentials to this repository.
