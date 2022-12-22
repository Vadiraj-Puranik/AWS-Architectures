# AWS Monitoring and Logging 


## AWS CloudWatch 
Cloudwatch is used for performance monitoring , alarms , Log collections and automated actions <br>
* CloudWatch Metrics : Services sends timely data for monitoring 
* CloudWatch Alarms : Monitoring the metrics and triggering appropriatet action
* CloudWatch Logs : Centralized collection of application and system logs
* CloudWatch Events : Events describing changes in AWS Resources 


## AWS CloudTrail
Caputres API Actions that occurs in AWS Account (CLI, SDK and Console).<br>
* Management Events : Provides information on management operations performed on the resources 
* Data Events : Provides information on resource operations performed and on what resource 

## AWS EventBridge 
EventBridge also known earlier as cloudwatch events. 
EventBridge has the event sources(AWS Services, Saas Apps, Custom Apps etc) , it takes these events , sends to Eventbridge bus and EventBridge Bus moves the data <br>
Targets such as Lamda, Kinesis , SNS Topic etc

