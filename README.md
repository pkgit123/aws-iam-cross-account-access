# aws-iam-cross-account-access
Playbook to configure AWS cross account access

See steps from ACloudGuru course on AWS Certified Developer Associate, Chapter 10.6 Configuring Cross Account Access Demo.

In this demo, enable a user in DEV account to access S3 bucket in PROD account.  See attached files.  

1. From PROD account, create IAM policy (see prod-iam-policy.json).  Update the S3 ARN, but keep suffix "/*".
1. From PROD account, create IAM role.  Specify "type of trusted entity" as "another AWS account".  Name the PROD IAM role: MyDevelopersAccess.  Attach IAM policy.
1. From DEV account, go to IAM Group, attach inline policy (see dev-iam-assume-role.json).  Update ARN with PROD-account-id and PROD-IAM-role.  
1. From DEV account, login as IAM user within IAM Group.  Once logged-in, select "Switch Role".  
1. Now the DEV account IAM user can see S3 buckets in PROD.  
