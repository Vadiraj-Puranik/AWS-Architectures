# AWS Databases 
![download](https://user-images.githubusercontent.com/113619300/209463599-dfa9dcf2-6db1-40a2-b79d-9699815a789c.jpg)

## Relational Databases (AWS RDS).
* MySQL
* Aurora
* PostgreSQL
* Microsoft SQL Server
* Oracle 
* MariaDB


#### Creating the RDS Instance with MySQL.

Step 1: Launch a EC2 instance to connect to RDS Instance.
![image](https://user-images.githubusercontent.com/113619300/209464703-7eb943d9-05ea-4151-a3da-b8ce27735a33.png)


Step 2: Allow 3306 Port in the Security group attached.
![image](https://user-images.githubusercontent.com/113619300/209464770-4e632670-5a0f-4981-8a89-a0311f16f45d.png)

Step 3: Go to RDS Console and create a RDS Instance and add DB name, Master username and password.
![image](https://user-images.githubusercontent.com/113619300/209464932-fab454a3-8645-47c8-b2c8-1e975b67e4c1.png)


Step 4: Choose connect to EC2 and select your ec2 instance from the dropdown
![image](https://user-images.githubusercontent.com/113619300/209464987-234b7303-7a05-4bdf-9b77-8d04c41edffa.png)

Step 5: Choose your security group with inbound rule of 3306 added and select the authentication as password .
![image](https://user-images.githubusercontent.com/113619300/209465042-67c5b987-380c-4a97-bafe-68f9c4d43eba.png)

Step 6: Click on your created database and copy the endpoint 
![image](https://user-images.githubusercontent.com/113619300/209465258-13657bed-c8ff-4708-8da8-3051a2b1ed31.png)

Step 7 : Use below command from EC2 instance to connect to the Database Instance 
```sh
mysql -u admin -p -h [endpoint]
mysql -u admin -p -h db-test-vadiraj.c3wtlfuodbsv.us-east-1.rds.amazonaws.com
```
![image](https://user-images.githubusercontent.com/113619300/209465667-e5e83011-6a93-467b-9af9-686f742b2c44.png)



#### Creating Read Replica for RDS Instance.
To create a Read Replica select the db and choose Action and click Read Replica.
![image](https://user-images.githubusercontent.com/113619300/209465781-73c7e8b5-96f4-4ed0-8e9c-1820f6ca25fc.png)

Choose the appropriate options available from the create Read Replica window and click create.
![image](https://user-images.githubusercontent.com/113619300/209465826-318537ed-f669-488a-96b6-0136c13687b9.png)


#### Failover the RDS Instance.
If the instance is rebooted or stopped and if you have enabled Multi-Az deployment Automatically the secondary instance which has synchronous communication becomes primary instance to serve the requests.




## AWS Aurora.

AWS Aurora is a AWS developed RDS which provides better scalability and availablity.<br>
Key Features:<br>
MySQL and PostgreSQL Compatible .<br>
5 Times faster than Mysql and 3 Times faster than PostgreSQL.<br>

Architecture of Aurora.<br>
Its constrined only to a region and each AZ will have read replicas(Max 15).<br>
All the read replicas will share the single Logical volume that is spanned over the region.<br>
Primary DB Instance will write data synchronosly on all the read replicas. Hence being Fault tolerant.<br>
At any point any of the read replicas can be promoted to be primary on occurence of outage.<br>
![AuroraArch001](https://user-images.githubusercontent.com/113619300/209466451-2c57ba5a-a2d0-430e-bb43-88607c871652.png)



## Non-Relational Databases
* AWS Dynamo DB

1:Composite Key = Partition key(primary) + Sort Key(Second part of a table's primary key which allows to sort or search among all items sharing the same partition key.)

2:Capacity Mode : 
```sh
On demand : You pay for what is used, no need to allocate capacity units prior.<br>
Provisioned : You allocate capacity units and pay even if its not used.<br>
```

3:DynamoDB Streams: Time ordered sequence of item modifications in the DynamoDB table . The information is stored for 24 Hours <br>
4:DynamoDB Accelerator: Inmemory cache for DynamoDB. <br>
5:DynamoDB Global Tables: Multi master (Multi region + Multi Active) Table . Same DB has asynchronous replication between regions . Below image depicts the architecture <br>
![amazon-dynamodb-global-tables](https://user-images.githubusercontent.com/113619300/209469760-b106af24-270e-45a4-a225-f25b4d8c9549.jpg)



