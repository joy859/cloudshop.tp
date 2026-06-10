# Phase B2 — Week 4 (multi-cloud)

## Table

| Need | AWS | Azure | GCP |
|------|-----|-------|-----|
| VM | EC2 | Virtual Machines (Azure VM)|computer engine |
| Object storage | S3 | blob storage|cloud storage |
| DNS | Route 53 | Azure dns|cloud DNS |
| CI | CodeBuild | Azure DevOps Pipelines| CLOUD BUILD|

## Question

Why use **GitHub Actions** instead of installing Jenkins on your own VM? (5 lines)

GitHub Actions is easier to set up and use because it is fully integrated with GitHub repositories. It does not require managing servers, updates, backups, or security patches as Jenkins does. Workflows can be created directly in the repository using YAML files. GitHub provides the infrastructure needed to run the pipelines, reducing maintenance effort and cost. This allows developers to focus on building and testing applications rather than administering CI servers.