
#run a policy and upload logs to cloudwatch logs:
custodian run --log-group=/cloud-custodian/<dev-account>/<region> -s ./output <policyfile>.yml

#run a policy and upload logs to cloudwatch logs:
custodian run --log-group=/cloud-custodian/test/eu-central-1 -s ./output --region eu-central-1 -c test.yml 

#clear cloudcustodian cache, when you're testing frequently cache might become stale: 
rm -rf ~/.cache/cloud-custodian.cache

#Good read:
Using the mailer: https://github.com/1Strategy/cloud-custodian-demo/blob/master/usingTheMailer.md
Good Demo: https://github.com/1Strategy/cloud-custodian-demo
Cusodian Documentation: https://cloudcustodian.io/docs/overview/deployment.html

