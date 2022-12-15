## 10 Step Process in setting up your Elastic Load Balancer ##


### Step 1:  Creating two EC2 Instances in the selected region and two Availablity Zones(us-east-1a and us-east-1b) ###
![EC2Instances](https://user-images.githubusercontent.com/113619300/207928911-5794296a-8fcb-4dcf-b830-406735a51e16.png)

### Step 2: Create a security group ELB-SecurityGroup with appropriate inbound and outbound rules ###

### Step 3: Create a Target group(ELB-Target) for Elastic load balancer which acts as a target for the incoming load ###
### Step 4: Add the above created EC2 Instances to the Target Group and wait for the registration to be completed ###
![Targets](https://user-images.githubusercontent.com/113619300/207940162-cc913ec4-8739-47c4-a379-7d4075464ce6.png)

### Step 5 Make sure that the targets registerd are in healthy state ###
![Targetsum](https://user-images.githubusercontent.com/113619300/207942331-09592638-529f-4237-a7e3-e5fda17678dd.png)


### Step 6: Create a Load Balancer and select scheme to be internet facing as our ELB is public internet facing and select the IP Address type of the traffic ###
![Loadbalancer](https://user-images.githubusercontent.com/113619300/207940667-d6d1a48e-142d-472b-af12-900975e3897e.png)

### Step 7: Select the availablity zones of the load balancer having the instances available , here we can note that both the EC2 instances are launched in the 2 availabilty zones adhering for fault Tolerance. ELB is a Region specific service spanned over the all AZs of the Region
###
![AZs](https://user-images.githubusercontent.com/113619300/207941338-d156face-2a04-49d7-a146-1e0b235eb7fe.png)


### Step 8: Add the listener to port 80 as we are using HTTP Application Load Balancer and attach your target group ###
![Listner](https://user-images.githubusercontent.com/113619300/207941929-cde68a2f-62ce-4a20-b931-2357c2161b62.png)


### Step 9: Verfying the summary of our ELB Configration ###
![Summary](https://user-images.githubusercontent.com/113619300/207941530-8b87d703-7de2-4ac3-b2ea-81a7b1b7b57a.png)

### Step 10: Get the DNS of the ELB and paste it on your browser to view the distributing of the load between Avaialabilty Zones in a region ###
![Server1](https://user-images.githubusercontent.com/113619300/207942957-12ac0a20-2304-44f2-88a3-40ff9718b392.png)

![Server 2](https://user-images.githubusercontent.com/113619300/207943000-db02fa83-856d-409d-be76-46c609aa3c7c.png)

#### CPU Spikes ####
![sO](https://user-images.githubusercontent.com/113619300/207950822-55751b0c-e192-434d-b7d2-7d451720a325.png)


















