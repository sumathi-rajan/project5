# Web Application: Fitness Training NEOGYM
## Description:
Launched "Fitness Training NeoGym," an innovative web application that prioritizes a seamless user experience, even during scheduled or unexpected downtime, thanks to the robust integration of AWS services.Utilized AWS services to enhance the availability and resilience of the Fitness Training NeoGym web application, ensuring an uninterrupted user experience in the face of potential disruptions.
## Services
* S3
* IAM Role
* EC2
* Application Load Balancer(ALB)
* Auto Scaling Group(ASG)
* Cloudwatch
* Simple Notification Service(SNS)
## step 1 - create s3 bucket
* Ensure all essential deployment files for web application are stored in an organized manner within an Amazon S3 bucket.
* Opt for a secure approach by either making all objects in the bucket public or implementing a bucket policy to control and restrict access to specific users.
## step 2 - IAM Role
* Define a dedicated IAM role tailored for the deployment instance, ensuring it possesses the essential permissions for secure access to the S3 bucket. Notably, for this project, the IAM role should be configured with S3 full access permissions.
## step 3 -Launch EC2
* Provision an EC2 instance with fundamental specifications including the AMI, instance type, and a key pair for secure third-party tool access to the EC2 instance.
* In the instance profile, associate the IAM role crafted in step 2, enabling the EC2 instance to securely access objects within the S3 bucket.
* Generate user data to facilitate the pre-installation of packages required for bootstrapping when attaching it to the EC2 instance during startup.
* Proceed to launch the instance as outlined in the previous step, incorporating the user data to ensure the pre-installed packages are seamlessly integrated during the instance's initialization.
## step 4 -Application Load Balancer(ALB)
* Establish an application load balancer with a specified name, configure it as internet-facing, and map network traffic to specific Availability Zones to efficiently manage traffic distribution.
* Specify HTTP listener ports to define the routes through which traffic should be directed for effective request handling.
* Define a target group to register instances, ensuring that traffic is only directed to instances in a healthy state, thereby optimizing the overall system performance.
## step 5 -security Group
* For the Security Group (SG) associated with the Application Load Balancer (ALB), adjust the inbound rules to permit internet traffic, providing users with straightforward access.
* Configure the Security Group (SG) linked with the instances to exclusively permit traffic originating from the Application Load Balancer (ALB), ensuring a secure and controlled communication channel.
## step 6 -configure ALB
* After configuring the Application Load Balancer (ALB), it furnishes a DNS name that facilitates seamless access to instances without the need for direct internet connectivity. Importantly, external users can exclusively access the instances through the ALB, ensuring a controlled and secure point of entry.
* In my project, I've configured the network mapping to encompass two availability zones, namely ap-south-1a and ap-south-1b. Additionally, I've registered targets within these specified availability zones, aligning with the instances I deployed in each zone. 
## step 7 -Auto Scaling Group(ASG)
* Implement an Auto Scaling Group (ASG) to dynamically manage the number of instances in response to varying workloads. This ensures optimal resource utilization and system availability by automatically adjusting the instance count based on configured scaling policies.
* In the context of my project, configuring the Auto Scaling Group (ASG) with a minimum capacity of 1, a desired capacity of 2, and a maximum capacity of 3
* With these settings, your ASG will automatically adjust the number of instances between 1 and 3 based on demand. If demand increases, the ASG may scale out to accommodate, and if demand decreases, it may scale in to reduce costs while maintaining a minimum level of capacity. This dynamic scaling ensures your application can handle varying workloads efficiently.
* To streamline the deployment process, consider initiating the setup with an Auto Scaling Group (ASG). Launch a new template encompassing the previously specified settings, including the creation of a load balancer with the designated target group.
## step 8 -Target Tracking policy
* I've implemented a target tracking policy within  Auto Scaling Group (ASG) to efficiently manage CPU utilization. When the CPU exceeds 50%, the policy dynamically scales up the ASG, automatically adding instances to handle increased demand. Conversely, when the CPU drops below 35%, the policy triggers a scale-down action, reducing the number of instances during periods of lower utilization.
* This proactive and automated approach ensures optimal performance and resource utilization, aligning with both the demands of  application and cost-effective scaling practices.
## step 9 -Cloudwatch
* Amazon CloudWatch is a comprehensive monitoring and observability service provided by AWS. It allows you to collect and track metrics, collect and monitor log files, and set alarms.
* Utilize the inherent integration between the Auto Scaling Group (ASG) and Amazon CloudWatch for seamless and automated monitoring.
* By employing a target tracking policy, the monitoring process becomes more refined, allowing you to closely track and regulate key metrics such as CPU utilization.
* This approach ensures that your ASG can dynamically respond to changing conditions, automatically scaling up or down to maintain optimal performance and resource utilization.
## step 10 -Simple Notification Service(SNS)
* I have set up an Amazon SNS topic to facilitate email notifications for Auto Scaling Group (ASG) scaling events. To receive these notifications, you'll need to subscribe to the SNS topic.
* This configuration ensures that you are promptly informed via email when the ASG scales up or down, enhancing awareness and allowing for timely responses to changes in AWS environment.
## Conclusion
In conclusion, the successful launch of "Fitness Training NeoGym," a state-of-the-art web application, is marked by its commitment to delivering a seamless user experience. This achievement is attributed to the robust integration of AWS services, which not only ensures uninterrupted availability but also enhances the application's resilience. Even in the event of scheduled or unexpected downtime, the utilization of AWS services has proven instrumental in maintaining the reliability of the Fitness Training NeoGym platform, thereby prioritizing user satisfaction and usability under various conditions.
















