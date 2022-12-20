### AWS Organizations 

![aws_organizations_structure_with_scps](https://user-images.githubusercontent.com/113619300/208633012-b5b31c73-cd69-4697-9da6-03f369e4130d.jpg)


AWS Organizations is a service which provides multi account management strategy to the AWS Environments
Two basic uses of the AWS Organizations is as below:

* Consolidated Billing 
* Service Control Polices 
* Provides APIS to create multiple accounts in AWS Programatically 

## Consolidated Billing:

Consolidated Billing option provides you with a management account and linked account . The advantages of using consolidated billing is as below
* Centrally manage all the AWS Accounts
* Billing discounts on large volumne of service usage 
* Limit of 20 accounts by default 
* Single view for all the charges of the multiple accounts


## Service Control Policies:

* SCPs provide maximum allowed permissions and are applied over the OUs(Organization Units)
* SCPs Affect only IAM Users and Roles and not Resources polices 
* SCPs basically controls the available permissions

## Control Tower

Control Tower is a region specific service 
Landing zone is basically a collection of multiple AWS Accounts having guradrails (Preventive and Detective)






