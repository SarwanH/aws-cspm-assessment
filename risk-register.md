# Risk Register

| Risk ID | Risk Description | Affected Asset | Likelihood | Impact | Severity | Business Impact |
|--------|------------------|---------------|------------|--------|----------|----------------|
| R-01 | Over-permissive IAM user with admin access | IAM (`cspm-test-user`) | High | High | Critical | Full AWS account takeover |
| R-02 | MFA not enabled on IAM user | IAM (`cspm-test-user`) | High | High | Critical | Unauthorized access via stolen credentials |
| R-03 | Long-lived access keys in use | IAM (`cspm-test-user`) | High | High | Critical | Persistent attacker access |
| R-04 | Publicly accessible S3 bucket | S3 (`public-test-bucket`) | High | High | Critical | Public data exposure |
| R-05 | S3 bucket not encrypted | S3 (`public-test-bucket`) | Medium | Medium | Medium | Data exposure if storage is compromised |
| R-06 | CloudTrail not enabled in all regions | CloudTrail | Medium | Medium | Medium | Incomplete audit logging |
| R-07 | GuardDuty not enabled | Account-wide | Medium | Medium | Medium | Delayed threat detection |
