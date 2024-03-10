* S3 buckets are not encrypted, objects are
* Each object in a bucket might be using different encryption settings

## Encryption At Rest

### Client Side Encryption
* The objects are encrypted by client & S3 receives the encrypted data
* S3 never sees the unencrypted version
### Server Side Encryption
* S3 takes the unencrypted versions. Then it encrypts & saves encrypted objects
* SSE-C - Customer Provided Keys
    * Key is provided by Customer
    * Encryption happens on AWS. 
    * Encrypted Object & Hash of the key used for encryption is stored in S3. The key itself is destroyed.
    * To decrypt the Key used to encrypt needs to be provided. S3 validates it against hash & then returns decrypted object.
* SSE-S3 - Amazon S3 Managed Keys ( Default)
    * Client only provides the object.
    * S3 generates key for every object it encrypts.
    * Client has no control over Creation, Management or Rotation of keys. Its entirely managed by S3
    * Each of the key is encrypted by using another key & encrypted object , key are stored together
    * The downside is role sepeation is not possible. Anybody who has access to creation of keys i.e. Full S3 Administrator can encrypt or decrypt data
* SSE-KMS - KMS Managed Keys
    * Here instead of S3, KMS managed key is used
    * S3 requests a new DEK to be generated using a KMS key
    * KMS returns plaintext & ciphertext version of DEK
    * S3 uses plaintext DEK to encrypt the data & then discards the plaintext key
    * Encrypted data & ciphertext DEK is stored.
    * If S3 Administrator does not have access to KMS key, he can't decrypt S3 objects. This way role seperation can be achieved.

### Encryption Types Summary

| Method | Key Management | Encryption Responsibility | Comments |
| ------- | ------------- | ------------------------- | -------- |
| Client Side | User | User | Plain text version never seen by AWS |
| SSE - C | User | S3 | - |
| SSE - S3 | S3 | S3 | No control over Key lifecycle, no role seperation |
| SSE - KMS | KMS | S3 | Role Seperation.Key Lifecycle Control |