# rosa-sts-aws-secrets-manager
 Integrating ROSA STS with AWS Secrets Manager

### AWS Side
1. Create AWS Secrets Manager with cloudformation in base/aws/, pass the OIDC endpoint without HTTPS://


### ROSA Side
1. Install Secret Store CSI Driver using Operator Hub

2. Install AWS Provider secret store and configurions with oc apply -f base/rosa/

3. Set ARN from Role into default Service Account in applications namespace: 
eks.amazonaws.com/role-arn: 'arn:aws:iam::508429907287:role/AssumeFromOIDC'