## Object Encryption
- Server-Side Encryption
    1. Amazon S3 Encryption - SSE-S3
        + Encryption using keys handled, managed, owned by AWS
        + Encryption type is AES-256
        + Enabled by default for new buckets & new objects
        + header: "x-amz-server-side-encryption": "AES256"
    2. Amazon S3 Encryption - SSE-KMS
        + Encryption using keys handled, managed by AWS KMS(Key Management Service)
        + header: "x-amz-server-side-encryption": "aws:kms"
        + Can be a bottleneck because of KMS throughput limitation
    3. Amazon S3 Encryption - SSE-C
        + Encryption using keys fully managed by customer outside of AWS
        + Clients include encryption key in header. S3 uses provided key to encrypt data before storing in bucket
        + Clients must include decryption key in header for data decryption

- Client-Side Encryption
    + Use client libraries like Amazon S3 Client-Side Encryption Library
    + Client encrypt data themselves before sending to S3
    + Client decrypt data themselves when receiving data from S3

## Encryption in transit (SSL/TLS)
- Amazon S3 exposes two endpoints:
    1. HTTP - non encrypted
    2. HTTPS - encryption in flight

- Force Encryption in Transit using policy
    + aws:SecureTransport

## S3 Cross-Origin Resource Sharing (CORS)
- Origin = scheme (protocol) + host (domain) + port
    + Example: https://www.example.com
    + protocol: https
    + domain: www.example.com
    + port: 443 for HTTPS
- Same origin: http://example.com/app1 = http://example.com/app2
- Different origin: http://www.example.com != http://other.example.com

- We need to configure S3 CORS for incoming request

## S3 - MFA Delete
- MFA is required to:
    1. Permanently delete an object version
    2. Suspend versioning on the bucket
- MFA is not required to:
    1. Enable versioning
    2. List delted versions
- Versioning must be enabled for MFA delete
- Only bucket owner (root account) can enable/disable MFA Delete


## S3 Glacier Vault Lock
- WORM (Write Once Read Many) Model
- When object is stored, it is no longer be changed
- Good for compliance and data retention

## S3 Object Lock
- WORM Model
- Block an object version deletion for a specified amount of time
- Retention mode:
    1. Compliance:
        + Object versions can't be overwritten or deleted by any user (root user included)
        + Object retention modes can't be changed, retention periods can't be shortened
    2. Governance:
        + Some users have special permissions to change the retention or delete the object
- Retention Period: protect the object for a fixed period, it can be extended
- Legal Hold:
    1. Project the object indeffintely, independently from retention period
    2. Can be freeely placed or removed using IAM permission

## S3 - Access Points