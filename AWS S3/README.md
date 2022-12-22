 ## AWS S3
 ![download](https://user-images.githubusercontent.com/113619300/209056927-6c1e2ff0-363b-41aa-92c4-3bb072f58ce1.png)


## S3 Storage classes :

* S3 Standard :S3 Standard offers high durability, availability, and performance object storage for frequently accessed data. Because it delivers low latency and high throughput, S3 Standard is appropriate for a wide variety of use cases, including cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics. 

 * S3 Intelligent Tiering: Automatically moving data to the most cost-effective access tier based on access frequency, without performance impact, retrieval fees, or operational overhead.
 
 * S3 Standard IA: S3 Standard-IA is for data that is accessed less frequently, but requires rapid access when needed. S3 Standard-IA offers the high durability, high throughput, and low latency of S3 Standard, with a low per GB storage price and per GB retrieval charge.
 
 * S3 One Zone IA : One Zone-IA is for data that is accessed less frequently, but requires rapid access when needed. Unlike other S3 Storage Classes which store data in a minimum of three Availability Zones (AZs), S3 One Zone-IA stores data in a single AZ and costs 20% less than S3 Standard-IA. 

* S3 Glacier (Instant Retrival) : Amazon S3 Glacier Instant Retrieval is an archive storage class that delivers the lowest-cost storage for long-lived data that is rarely accessed and requires retrieval in milliseconds

* S3 Glacier (Flexible Retrival) : S3 Glacier Flexible Retrieval delivers low-cost storage, up to 10% lower cost (than S3 Glacier Instant Retrieval), for archive data that is accessed 1—2 times per year and is retrieved asynchronously. For archive data that does not require immediate access but needs the flexibility to retrieve large sets of data at no cost, such as backup or disaster recovery use cases, S3 Glacier Flexible Retrieval (formerly S3 Glacier) is the ideal storage class.

* S3 Glacier Deep Archive : S3 Glacier Deep Archive is Amazon S3’s lowest-cost storage class and supports long-term retention and digital preservation for data that may be accessed once or twice in a year. It is designed for customers—particularly those in highly-regulated industries, such as financial services, healthcare, and public sectors—that retain data sets for 7—10 years or longer to meet regulatory compliance requirements. 


## IAM Policies :
Directly Applying the policies to users , groups or roles via IAM

## Bucket Policies :
Only attached to S3 buckets and apply to only that bucket.

## Access Control Lists(ACLs) :
Legacy method but these can be applied to bucket as well as at the object levels.

## S3 Versioning :
Keeping the multiple version of the object which helps in accidental deletion and overwrite.
For cross region or same region replication versioning must be enabled.

## S3 CORS(Cross Origin Resource Sharing) :


## S3 Lifecycle Rules :
Moving / Deleting the objects to various Storage classes 


## S3 Encryption:
```sh
S3 Encryption refers here at the data at rest in the buckets and below are few types of enryptions provided 
S3 Encryption with S3 managed keys: Encryption/Decryption with AWS Provided S3 keys
S3 Encryption with KMS managed keys: Encryption/Decryption with AWS KMS Provided keys
S3 Encryption with Client Provided keys: Encryption/Decryption with Client Provided S3 keys
S3 Encryption with Client Side Encryption: Encryption/Decryption proceessed by client before uploading on S3.
```

