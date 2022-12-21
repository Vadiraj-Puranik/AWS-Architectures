## Route 53
![Route53](https://user-images.githubusercontent.com/113619300/208885194-4a8c44b1-6a05-4e0e-a2eb-825e68dac808.png)


Route 53 Provides the DNS and Routing services in the AWS Cloud and below are few things Route 53 helps in 

* Hosted zone 
* Domain Registration 
* Health Checks of Endpoints
* Routing/ Traffic flow Polices 

## Hosted Zone:
This represents the records belonging to the specific domains.Hosted zones can be either public or private

* Public Hosted zone: Web server in the public subnet serving the clients (ex : ICICI.com)
* Private Hosted zone: Internal Hosted Zones( ICICI.local communicating internally (Ec2 with db servers etc)).<br>
In Private Hosted Zone Route 53 Hosted Zone will be associated with the VPC 


## Domain Registration with Route 53:

* Search for Route 53 <br>
* Click on Domain Registration
 ![image](https://user-images.githubusercontent.com/113619300/208888753-a57c1038-f7c7-4ac7-8cfe-3c97219a5253.png)
* Find the domain your intrested and add to the cart
![image](https://user-images.githubusercontent.com/113619300/208889096-cdc53c71-57b1-4892-82da-47513e11eb00.png)
* Add the contact and email details and proceed ahead to purchase
* Now Your Domain will be available in Hosted zones and you can proceed ahead and create records 

## Health Checks of Endpoints :
Route 53 monitors the Health of the resources and routes to appropriate targets when outage occurs 
![image](https://user-images.githubusercontent.com/113619300/208892839-79447ca6-2dcc-4776-9161-bed6acad378a.png)




## Routing/ Traffic flow Polices : 

```sh
Simple : Providing IP associated with Domain name
Failover : If Primary IPs Health Check fails serves the secondary IPs
Geo-location : Uses Geolocation of the user and routes to the closest region
Geo-proximity : Routing withing Geolocation to closest proxity area( Basically Closest area in geographic location)
Latency : Routing based on lowest latency route 
Multivalue Answer : Returns multiple IPs functioning as Load Balancers
Weighted : Routes based on the assigned weights.(Ex 40 % traffic to one record and remaining 60% to other record.)
```
