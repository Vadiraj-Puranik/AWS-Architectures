## AWS CloudFront 
![cloudfront](https://user-images.githubusercontent.com/113619300/208918558-bec838ab-09bb-4c9c-8730-87eafe893385.png)



## Cloudfront Origins and Distributions 
CloudFront Origin = These are the sources from which the data is being distributed . They can be your load balancers , S3 buckets, MediaStore Container and MediaPackage containers.CloudFront Origin is basically location where the data is stored.
Distributions = You create a CloudFront distribution to tell CloudFront where you want content to be delivered from, and the details about how to track and manage content delivery.


## Caching behaviours 
Below diagram depicts the cahing behaviour (Cache Hit and Cache Miss)<br>
![download](https://user-images.githubusercontent.com/113619300/208932638-b6c4e9aa-dbe1-4e0b-8ce5-b237afd499d5.png)


## 5 Steps in creating your CloudFront Distribution :

### Step 1 : creating 2 S3 bucket origins:
![image](https://user-images.githubusercontent.com/113619300/208923305-fc114248-b960-4207-bfec-61b8e5b6b518.png)

* mys3-origin1 bucket has .png files 
![image](https://user-images.githubusercontent.com/113619300/208923482-61de2494-344f-43ed-8c38-970c0df4dd1c.png)

* mys3-origin2 bucket has .pdf files 
![image](https://user-images.githubusercontent.com/113619300/208923653-52990485-9efc-49d1-98fb-3aaff3a30e19.png)


### Step 2 : Create a CloudFront Distribution and choose the origins
![image](https://user-images.githubusercontent.com/113619300/208923996-3246df95-5ae0-469e-b57a-d50923234501.png)

You can choose the price class according to requirement of cloudFront.
![image](https://user-images.githubusercontent.com/113619300/208925177-6860a83a-8cbd-4610-8ea2-4f4ee4ce1e77.png)


Deploy your cloudFront Distribution and wait for status to be enabled 



### Step 3: Go on to your distribution and create origin for your mys3-origin2 Bucket which hosts .pdf files 
![image](https://user-images.githubusercontent.com/113619300/208926220-818d3547-b109-4bdd-b4da-4cf42092d933.png)

### Step 4 : Click on behaviour and create a behaviour you want to add for your cloudfront distribution and save the changes 
![image](https://user-images.githubusercontent.com/113619300/208926785-f575a95e-0e9d-4dab-a523-9921ab66410b.png)


## Step 5 : Copy the DNS of the CloudFront Distribution and below are the results
* Path .png with same distribution shows as below 
![image](https://user-images.githubusercontent.com/113619300/208929541-85b574b3-262f-4438-8561-63d12db1e721.png)


* Path .pdf with same distribution shows as below 
![image](https://user-images.githubusercontent.com/113619300/208929733-104a43cb-c260-449f-850f-d03cce778d2c.png)


