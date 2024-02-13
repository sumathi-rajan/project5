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
*After configuring the Application Load Balancer (ALB), it furnishes a DNS name that facilitates seamless access to instances without the need for direct internet connectivity. Importantly, external users can exclusively access the instances through the ALB, ensuring a controlled and secure point of entry.
## step 7 -Auto Scaling Group(ASG)




















