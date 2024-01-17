# tfsec_main

This GitHub action makes use of Tfsec which is a tool developed by Aqua security to scan Terraform files for potential security issues. A high level workflow has been depicted in the image below for reference. 

![image](https://github.com/aksh7sharma/tfsec_main/assets/21289967/fe7eaf7a-b71c-47d2-8620-1007968fb19d)

1. A Git pull request or push request is issued which is the trigger for the GitHub action to run.
2. The GH runner fetches the Tfsec binary which is version controlled from a S3 bucket.
3. The first job scans all the TF files included in the present GH repo and uploads the results as a release asset in markdown format. The job also publishes a PR comment with a link to the release asset published.
4. The second job checks for the TF files which are being modified with the current PR and only scans those files. The results are published as a PR comment with relevant findings.
5. Depending on the job output, the PR is given a Green or Red status. The tool has been configured in such a way that the PR is not blocked in any scenario (soft-fail).

More details to be added soon!

