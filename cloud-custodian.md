# Cloud Custodian cheat-sheet

[Cloud Custodian](https://github.com/cloud-custodian/cloud-custodian) is a tool that unifies the dozens of tools and scripts most organizations use for managing their AWS accounts into one open source tool. It’s a stateless rules engine for policy definition and enforcement, with metrics and detailed reporting for AWS.

Organizations can use Custodian to manage their AWS environments by ensuring compliance to security policies, tag policies, garbage collection of unused resources, and cost management via off-hours resource management, all from the same place. Custodian policies are written in simple YAML configuration files that specify given resource types and are constructed from a vocabulary of filters and actions.

Their docs: [here](https://cloudcustodian.io/docs/index.html).

Here are some commands that I use to make my life a bit easier:

### run a policy and upload logs to cloudwatch logs:
```
$custodian run --log-group=/cloud-custodian/<dev-account>/<region> -s ./output <policyfile>.yml
```

### run a policy and upload logs to cloudwatch logs, scope to a particular region (Frankfurt in this example):
```
$custodian run --log-group=/cloud-custodian/eu-central-1 -s ./output --region eu-central-1 -c test.yml 
```
### clear cloudcustodian cache, when you're testing frequently cache might become stale: 
```
$rm -rf ~/.cache/cloud-custodian.cache
```

## Good read:

Using the mailer: https://github.com/1Strategy/cloud-custodian-demo/blob/master/usingTheMailer.md

Good Demo: https://github.com/1Strategy/cloud-custodian-demo

Cusodian Documentation: https://cloudcustodian.io/docs/overview/deployment.html
