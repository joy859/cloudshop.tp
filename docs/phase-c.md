# Phase C — Week 5 (DevOps pipeline)

## Your pipeline diagram

```
Local code → git push → GitHub Actions → tests → docker build
```

State: where does it **stop** if a test fails? What stays **manual** in your setup?

The pipeline stops at the Run Tests stage. The Docker image is not built, and the workflow is marked as failed.it can also sop a install dependencies i he network connection is no stable

-What stays manual in your setup?

The developer must manually write code, push changes to GitHub, review the workflow results, and run/deploy the Docker container locally.v

## Questions

1. DevOps in one sentence:

DevOps is a practice that combines software development and IT operations to deliver applications quickly, reliably, and continuously.

2. Two measurable DevOps goals:

-Increase deployment frequency (deploy updates more often).

-Reduce deployment failures and recovery time when issues occur.

3. What remains manual in **your** lab:

Writing the code, committing and pushing changes to GitHub, reviewing the GitHub Actions results, taking screenshots, and testing the Docker container locally remain manual tasks.