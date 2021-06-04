# Step 3: CONFIGURING RDS DATABASE

It is critical to secure your database from unauthorized access, and there are a number of strategies you can use to add security to your database. You will learn two of them in this module. They are:

- Network security: Limiting access to your database instance by rejecting traffic that’s not from authorized IP addresses
- Password authentication and authorization: Limiting access to your database by requiring a username and password to access.
We will configure each of these in the steps below.

## Allow EC2 Instance to Access RDS Database 
So Select created Database ,like wordpressDB this our database name.
First, we will modify our RDS database to allow network access from created EC2 instance.In the previous step, we created security group rules to allow SSH and HTTP traffic to your WordPress EC2 instance. The same principle applies here. This time, we want to allow certain traffic from our EC2 instance into our RDS database.
To configure this, go to the RDS databases in the AWS console. Click on the MySQL database you created in an earlier step.

![create_db](https://user-images.githubusercontent.com/60148173/120812035-3f0db400-c56a-11eb-81fa-527121acb48a.PNG)

- Scroll to the Connectivity & security tab in the display, and click on the security group listed in VPC security groups.

![go_to_vpcsecurity](https://user-images.githubusercontent.com/60148173/120812490-a3c90e80-c56a-11eb-897a-0578a3245bea.PNG)

- The console will take to the security group configured for our database. Click the Inbound tab, then click the Edit button to change the rules of security group.
The default security group has a rule that allows all inbound traffic from other instances in the default security group. However, since our WordPress EC2 instance is not in that security group, it will not have access to the RDS database.
Change the Type property to MYSQL/Aurora, which will update the Protocol and Port Range to the proper values. Then save this

![select_wordpress_sg](https://user-images.githubusercontent.com/60148173/120812727-e0950580-c56a-11eb-8c9f-79f325872556.PNG)

# Create Database User
- connect to your MySQL database.First, run the following command in terminal to install a MySQL client to interact with the database.
> sudo yum install -y mysql

![install_mysql](https://user-images.githubusercontent.com/60148173/120809101-61ea9900-c567-11eb-9367-88834948cccd.PNG)

- Next, find the hostname for your RDS database in the AWS console. In the details of your RDS database, the hostname will be shown as the Endpoint in the Connectivity & security section.
![select_endpoint_rds](https://user-images.githubusercontent.com/60148173/120809784-0c62bc00-c568-11eb-9ef4-716139ef27c9.PNG)

- In terminal, enter the following command to set an environment variable for your MySQL host. Be sure to replace “<your-endpoint>” with the hostname of your RDS instance.
> export MYSQL_HOST=<your-endpoint>
 
 ![replace](https://user-images.githubusercontent.com/60148173/120809990-42a03b80-c568-11eb-9b33-3da8a2e17e01.PNG)
 
 - Next, run the following command in terminal to connect to your MySQL database. Replace “<user>” and “<password>” with the master username and password you configured when creating your RDS database.
 > mysql --user=<user> --password=<password> wordpress
 - If we connected successfully, our terminal should indicate connection to the MySQL database as shown in the following image.
 
 ![connect_msql](https://user-images.githubusercontent.com/60148173/120810412-a6c2ff80-c568-11eb-95f5-e8ec8579eaad.PNG)

 - Finally, create a database user for your WordPress application and give it permission to access the “wordpress” database.
 - Run the following commands in your terminal:
 ```
CREATE USER 'wordpress' IDENTIFIED BY 'wordpress-pass';
GRANT ALL PRIVILEGES ON wordpress.* TO wordpress;
FLUSH PRIVILEGES;
Exit
```
 
 ![database_user](https://user-images.githubusercontent.com/60148173/120810519-bfcbb080-c568-11eb-8812-81e085ece299.PNG)

 In the next step, we will configure our EC2 instance to run the Wordpress application.Select [Step4](configure_wordpress_ec2.md)





 

