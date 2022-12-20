
# AWS VPC(Virtual Private Cloud)


VPC is spanned across region , there is a default VPC which is already setup and if you dont specify VPC then resources are usually moved in default VPC.
It is important to note that default VPC is public as IG is attached.


## VPC Components ##

* Public and Private Subnets 
```sh
First 4 IPs and last IP are reserved by AWS as below 
First IP : Network ID 
Second IP : VPC Router 
Third IP : DNS Server
Fourth IP : Future use
Last IP : Broadcast address
ex: 10.0.0.0/24 
32-24= 8 bits for Host
Host bits = 8
Total Hosts IPs Available = 256 -5(Reserved)=251
```

* Internet Gateway -> Virtual Route to Internet which also performs NAT
* Route Tables(Logical Routers)-> Central routing systems for the AZs and the VPC . There is main table present which is associated with Default VPC
* NAT Gateway -> Connecting Private instances to access Internet . Elastic IP needs to be associated with the NAT Gateway
* Security Groups -> Firewalls at Instance level. This is a STATEFUL(Inbound allowed then Outbound is allowed as well) Service.
* NACL -> Applicable at the subnet level and provided allow and deny rules . This is STATELESS service.



## Steps in creating your first VPC:

* Step 1: Create a VPC and add CIDR Values 
![image](https://user-images.githubusercontent.com/113619300/208654744-e0e668c4-abcc-411c-a182-24520392f2c2.png)

* Step 2: Create a Subnet 
![image](https://user-images.githubusercontent.com/113619300/208656127-1e4fb8be-f503-4b98-ac42-aa38f7856b19.png)

* Step 3: Create a Internet Gateway and attach it to VPC Created
![image](https://user-images.githubusercontent.com/113619300/208656515-bc5fae28-d3eb-4972-b72a-a09dea897983.png)

* Step 4: Create a Route Table and attach the subnet to the route table 
![image](https://user-images.githubusercontent.com/113619300/208656715-a65096f1-d1a1-4ad3-be4c-0d09aa3cb4f7.png)


Deleting the VPC will delete associated subnet,IG and Routes 

Diagrammatic view for reference
![image](https://user-images.githubusercontent.com/113619300/208665578-8018c63c-854c-451b-a059-3c724dd9cf0d.png)




