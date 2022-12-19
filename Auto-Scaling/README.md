## Auto Scaling of EC2 Instances Demo ##

Auto Scaling is region specific and in order to have High availablity it is suggested to have instances into multiple Availability Zones
![ELB-ASG](https://user-images.githubusercontent.com/113619300/208427359-64e96efa-4752-4ef1-882e-c0daab729fd0.png)

## Components of Auto-Scaling:

* Lauch Templates
* Auto-Scaling Groups
* Scaling Policies 

## Scaling Polices:
```sh
Target Tracking Policy :Target tracking policy lets you specify a scaling metric and metric value that your auto scaling group should maintain at all times. (Scale out and Scale in based on metric). For example: CPUUtilization to be 75% and it makes sure that the metric is balanced with scale in and scale out.
Simple Scaling Policy :Simple scaling relies on a metric as a basis for scaling. For example, Scaled when the util croses 75% and scale down its under 75%. 
Step Scaling Policy  : This is similar to Simple Scaling Policy with step values . For example, Scale 2 instances when Utilization reaches 75% and 2 more instancs when Utilization reaches 90%.
```

## Demo : 

### Step 1 : Create a Launch Template which basically has all the required details on what should occur when ASG has a hit.
I have created a Lauch Template : VadirajLaunchTemplate

### Step 2:Currently we observe no instances are running
![Noinstances](https://user-images.githubusercontent.com/113619300/208433339-673441fd-0062-440d-ba6b-5414fd91520a.png)

### Step 3: Go ahead to create a Auto Scaling Group , we observe that the dropdown will auto-populate the Launch Template if you have already created it.
![image](https://user-images.githubusercontent.com/113619300/208435851-a76defd7-a4ae-4486-b0ea-eeb95f3a8a4e.png)

### Step 4: Select the AZs and the VPC which you wish to launch
![image](https://user-images.githubusercontent.com/113619300/208436909-72f833f9-0983-4074-b36f-0ff9a4ee2356.png)

### Step 5: Choose the Load balancer if you already have a ELB setup . Else you can proceed ahead without ELB .
![image](https://user-images.githubusercontent.com/113619300/208437014-f72e1288-3bd7-49da-8cd1-42c81ef74d1e.png)

### Step 6: Choose the Auto Scaling group size and the scaling policy.

Currently I am going ahead with 2 Desired , 2 Minimum and 4 Maximum(If the load croses 4 instances the Auto Scaling group fails, make sure to have appropriate Maximum Instances)
![image](https://user-images.githubusercontent.com/113619300/208437690-2ebe95df-98d6-4881-b05b-5c8049050e4d.png)

Scaling Policy : I have selected Dynamic Target Tracking with CPU Utilization as the metric and target metric Usage to be 60%
![image](https://user-images.githubusercontent.com/113619300/208437824-6d7e5ed1-3b23-4036-9b3e-c93b2f05d76b.png)

### Step 7: Review All the details and launch the Auto Scaling Group.
![image](https://user-images.githubusercontent.com/113619300/208438090-6db8ad17-3a38-4a3d-b26b-07f41f6044b1.png)


Once the ASG is lauched we observe that the desired Instances are maintained 
![image](https://user-images.githubusercontent.com/113619300/208438286-b68026b5-ec98-493e-940b-d2a62240c48e.png)


### Step 8 : Currently we observe that 2 Instances are lauched which is the minimum and desired value mentioned in our ASG
![image](https://user-images.githubusercontent.com/113619300/208438586-21018b5b-391c-4990-b670-791cf598d2be.png)


### Step 9: Connect to both instances and induce stress in cross the target CPU utilization to 60% 
Use below commands to induce stress on the instances 
```sh
sudo amazon-linux-extras install epel
sudo yum install stress -y 
stress -c 6
```

Current CPU Utilization on both the instance Server 1: 44.204.242.205
![image](https://user-images.githubusercontent.com/113619300/208439976-5097887b-3799-4705-95c0-1b61d1618bdf.png)


Current CPU Utilization on both the instance Server 2 : 34.228.184.66
![image](https://user-images.githubusercontent.com/113619300/208440022-15984c57-d9a2-4980-b431-f209bf7c7362.png)


### Step 10 : We observe that alarms are being generated in CloudWatch 
![image](https://user-images.githubusercontent.com/113619300/208441282-1c00c7f5-1e6c-4ea6-b34a-ee84d39f61b2.png)

### Server 1 CPU Utilization after inducing stress

![image](https://user-images.githubusercontent.com/113619300/208441487-d19f1464-e8ef-4f34-910d-571e6ae5dc3a.png)

### Server 2 CPU Utilization after inducing stress

![image](https://user-images.githubusercontent.com/113619300/208441590-be01c00d-b4dd-4ed5-9f12-810dfd43916a.png)



### Step 11: As soon as CPU Utilization crosses 60%  we observe that a new instance i-0ebb5ea699ba406dd was added to balance the load 
![image](https://user-images.githubusercontent.com/113619300/208441706-c025f86c-8e38-4b83-b703-15d9d1807241.png)



CPU Utilization data from CloudWatch 
![image](https://user-images.githubusercontent.com/113619300/208442080-ee70be02-8116-4c4e-84ad-628e4b92c607.png)


As soon as you delete the ASG the instances associated are automatically terminated . If you wish to keep the instances alive you should manually detach the instance from ASG before ASG is deleted 
![image](https://user-images.githubusercontent.com/113619300/208444914-24fb1951-a8a3-49a2-9acf-8a1fb6e2336a.png)







