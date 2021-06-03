# CONFIGURING RDS DATABASE

It is critical to secure your database from unauthorized access, and there are a number of strategies you can use to add security to your database. You will learn two of them in this module. They are:

- Network security: Limiting access to your database instance by rejecting traffic that’s not from authorized IP addresses
- Password authentication and authorization: Limiting access to your database by requiring a username and password to access.
We will configure each of these in the steps below.

## Allow EC2 Instance to Access RDS Database 
So Select created Database ,like wordpressDB this our database name.
First, we will modify our RDS database to allow network access from created EC2 instance.In the previous step, we created security group rules to allow SSH and HTTP traffic to your WordPress EC2 instance. The same principle applies here. This time, we want to allow certain traffic from our EC2 instance into our RDS database.
To configure this, go to the RDS databases in the AWS console. Click on the MySQL database you created in an earlier step.

![create_db](https://user-images.githubusercontent.com/60148173/120693721-010b8400-c4c7-11eb-9dd6-cb334b4da9a5.PNG)

- Scroll to the Connectivity & security tab in the display, and click on the security group listed in VPC security groups.

![go_to_vpcsecurity](https://user-images.githubusercontent.com/60148173/120693906-36b06d00-c4c7-11eb-9c85-a104e67d9949.PNG)

- The console will take to the security group configured for our database. Click the Inbound tab, then click the Edit button to change the rules of security group.
The default security group has a rule that allows all inbound traffic from other instances in the default security group. However, since our WordPress EC2 instance is not in that security group, it will not have access to the RDS database.
Change the Type property to MYSQL/Aurora, which will update the Protocol and Port Range to the proper values. Then save this

![select_wordpress_sg](https://user-images.githubusercontent.com/60148173/120694216-90189c00-c4c7-11eb-89a2-f95a8132f496.PNG)

 

