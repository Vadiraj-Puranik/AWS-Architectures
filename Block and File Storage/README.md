
# Amazon EBS and EFS 
![image](https://user-images.githubusercontent.com/113619300/209119846-02aff96c-8063-4d57-adc7-76a5ea2ecef7.png)


# AWS Elastic Block Store (EBS)
EBS is constrained for AZs , Cannot be used by instance of another AZ unless you migrate the volume  <br>
One Instance can have multiple EBS volumes attached but the same volume cannot be attached to another instance at same time<br>
GP2 = Storage 1G -16T with 16,000IOPS<br>
IO1 = Storage 4G -16T with 64,000IOPS<br>
EBS volumes are attached via NIC card over a network to the instances while Instance Store volumes are physically attached to the host(on which EC2 runs).
EBS Snapshots are the Point in Time state of the instance which can be stored in S3

## Creating a EBS Volume :<br>
* Launch a EC2 Instance
![image](https://user-images.githubusercontent.com/113619300/209124138-48a7b80b-ec99-462b-b6ae-8a6829f06610.png)

* Go to Volumes and create a volume , choose appropriate Volume type. Make sure to choose the same AZ as the instance you want to attach to.
![image](https://user-images.githubusercontent.com/113619300/209124831-3d45fa7a-54c8-4af4-b6b3-5fe6b38b596b.png)


![image](https://user-images.githubusercontent.com/113619300/209125185-8622c3a7-0e9e-4bfa-803e-e2af2bd7f00f.png)

* Attach the volume to your instance . /dev/sdf is the new volume with 100G
![image](https://user-images.githubusercontent.com/113619300/209125556-42166c27-3f15-476b-a49b-d8177470453b.png)

* Login to your instance and verify if volumne is mounted 
![image](https://user-images.githubusercontent.com/113619300/209126684-3c6738d2-f584-422e-8746-1eeb9329bc59.png)


## Migrating EBS between the AZs :<br>

* Go to the volume and create a snapshot of the volume
![image](https://user-images.githubusercontent.com/113619300/209129384-f799fb24-c802-47ab-8142-3a54f8ff6293.png)

* Once snapshot is avaialble you can either create a volume and attach that to instance or copy snapshot to your required region
![image](https://user-images.githubusercontent.com/113619300/209129655-0e4a751c-82c6-42d2-afe7-d679882411d1.png)





# AWS Elastic File System (EFS)

Amazon Elastic File System (Amazon EFS) provides a simple, scalable, elastic file system for general purpose workloads for use with AWS Cloud services and on-premises resources.<br>
You can create a EFS in a VPC and Various resources can use it via NFS protocol simultaneously <br>
Cross Account/Region accessing the file-system is also possible via Peering connection.<br>
On-premise access is possible via VPN or Direct Connect.




