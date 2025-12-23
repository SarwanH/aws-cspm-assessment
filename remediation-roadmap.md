# Remediation Roadmap

| Priority | Risk ID | Issue | Recommended Action | Owner | Timeline |
|---------|---------|-------|--------------------|-------|----------|
| Critical | R-01 | Over-permissive IAM user | Remove AdministratorAccess and apply least-privilege IAM policies | Cloud Security | Immediate |
| Critical | R-02 | MFA not enabled for IAM user | Enforce MFA for all IAM users | Cloud Security | Immediate |
| Critical | R-03 | Long-lived access keys | Delete access keys and transition to IAM roles | Cloud Security | Immediate |
| Critical | R-04 | Publicly accessible S3 bucket | Enable S3 Block Public Access and restrict bucket policies | Cloud Security | Immediate |
| Medium | R-05 | S3 bucket not encrypted | Enable server-side encryption (SSE-S3 or SSE-KMS) | Cloud Ops | Short-term |
| Medium | R-06 | CloudTrail not enabled in all regions | Enable CloudTrail across all AWS regions | Cloud Ops | Short-term |
| Medium | R-07 | GuardDuty not enabled | Enable Amazon GuardDuty for continuous threat detection | Cloud Security | Short-term |
