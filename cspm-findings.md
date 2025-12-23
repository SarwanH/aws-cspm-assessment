**FINDING 1: Over-Permissive IAM User**

**Service**: IAM
**Resource**: cspm-test-user
**Control Area**: Identity & Access Management
**Severity**: High

**What is wrong**:
The IAM user "cspm-test-user" has the "AdministratorAccess" policy attached.

**Why this is a problem**:
Administrator access grants full control over the AWS account. If this user's credentials are compromised, an attacker could:

- Create new users
- Delete resources
- Exfiltrate data
- Disable logging

**CIS Reference**:
- CIS AWS Foundations Benchmark: 1.16 - Ensure IAM policies grant least privilege

________________________________________________________

**FINDING 2: MFA Not Enabled for IAM User**

**Service**: IAM
**Resource**: cspm-test-user
**Control Area**: Authentication
**Severity**: High

**What is wrong**:
Multi-Factor Authentication (MFA) is not enabled for the IAM user.

**Why this is a problem**:
Without MFA, account security relies only on a password or access key. Stolen credentials can be used immediately without additional verification.

**CIS Reference**:
- CIS AWS Foundations Benchmark: 1.2 – Ensure MFA is enabled for all IAM users

________________________________________________________

**FINDING 3: Active Long-Lived Access Keys**

**Service**: IAM
**Resource**: cspm-test-user
**Control Area**: Credential Management
**Severity**: High

**What is wrong**:
The IAM user has active access keys that do not expire automatically.

**Why this is a problem**:
Long-lived access keys are frequently leaked through:

- GitHub repositories
- Logs
- Compromised machines

Once leaked, they provide programmatic access to AWS resources.

**CIS Reference**:
- CIS AWS Foundations Benchmark: 1.4 – Rotate access keys regularly

________________________________________________________

**FINDING 4: Publicly Accessible S3 Bucket**

**Service**: Amazon S3
**Resource**: cspm-test-bucket-sh
**Control Area**: Data Protection
**Severity**: High

**What is wrong**:
The S3 bucket has public access enabled and does not have “Block Public Access” enforced.

**Why this is a problem**:
Public S3 buckets can expose sensitive data to the internet. This has been the root cause of many high-profile data breaches.

**CIS Reference**:
- CIS AWS Foundations Benchmark: 2.1.1 – Ensure S3 Block Public Access is enabled

________________________________________________________

**FINDING 5: S3 Encryption Not Enabled**

**Service**: Amazon S3
**Resource**: cspm-test-bucket-sh
**Control Area**: Data Encryption
**Severity**: Medium

**What is wrong**:
Server-side encryption is not enabled on the S3 bucket.

**Why this is a problem**:
If data is accessed improperly or underlying storage is compromised, unencrypted data may be readable.

**CIS Reference**:
- CIS AWS Foundations Benchmark: 2.1.1 – Enable encryption for S3 buckets

________________________________________________________

**FINDING 6: CloudTrail Not Enabled in All Regions**

**Service**: CloudTrail
**Resource**: Default trail
**Control Area**: Logging & Monitoring
**Severity**: Medium

**What is wrong**:
CloudTrail is enabled only in a single region instead of all regions.

**Why this is a problem**:
Attackers may operate in regions where logging is disabled, resulting in blind spots and incomplete audit logs.

**CIS Reference**:
- CIS AWS Foundations Benchmark: 2.1 – Ensure CloudTrail is enabled in all regions

________________________________________________________

**FINDING 7: GuardDuty Not Enabled**

**Service**: GuardDuty
**Resource**: N/A
**Control Area**: Threat Detection
**Severity**: Medium

**What is wrong**:
Amazon GuardDuty is not enabled in the AWS account.

**Why this is a problem**:
Without GuardDuty, malicious activity such as compromised credentials, unusual API calls, or known threat indicators may go undetected.

**CIS Reference**:
- CIS AWS Foundations Benchmark: 4.1 – Ensure GuardDuty is enabled



