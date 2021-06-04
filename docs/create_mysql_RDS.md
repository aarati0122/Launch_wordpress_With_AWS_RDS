# Step 2: Create Mysql by using RDS

At this point, you have created an RDS database and an EC2 instance. In this module, we will configure the RDS database to allow access to specific entities.
- To begin, go to Amazon RDS in the AWS console. Click the orange Create database button to get started.
The first step is to choose the database engine you want to use. Amazon RDS supports six different engines, from popular open-source options like MySQL and PostgreSQL, to commercial options like Oracle and Microsoft SQL Server,
to a cloud-native option called Amazon Aurora that was custom-built to take advantage of the cloud.WordPress uses MySQL, so select that engine now.

![rds](https://user-images.githubusercontent.com/60148173/120688555-d0285080-c4c0-11eb-9c54-2efdd572db3d.PNG)

- In the Templates section of the creation wizard, there is an option to only show options that are available in the AWS Free Tier. 
Select this option now if you would like to use this for learning without spending any money. Also select the Mysql version I select MySQL 8.0.20 .

![selectversion](https://user-images.githubusercontent.com/60148173/120689425-b76c6a80-c4c1-11eb-8688-2235a7bde966.PNG)

- In the Settings section, enter wordpressdb as your DB instance identifier you can give any name for your DB instance. Then specify the master username and password for your database. Choose a strong, secure password to help protect your database. 
Store the username and password for safekeeping as you will need it in a later module.

![settingdb](https://user-images.githubusercontent.com/60148173/120689992-56916200-c4c2-11eb-80ef-82017c711806.PNG)

- After this setting we need to set the value of instance class and storage details.In this project default setting will work because we select the free tier .
If you don’t want to use the AWS Free Tier, you could set a larger instance class or alter the storage configuration options.

![dbinstnceclass](https://user-images.githubusercontent.com/60148173/120690640-1a123600-c4c3-11eb-9d25-b2a268b397de.PNG)

![storage](https://user-images.githubusercontent.com/60148173/120690724-344c1400-c4c3-11eb-8b28-79f1a4cfe4e0.PNG)

- Next we configure the connectivity and network configuration.Amazon RDS instances must be created in an Amazon VPC, which is a logically-separate network where your provisioned resources will live.

![connectivity1](https://user-images.githubusercontent.com/60148173/120691029-9442ba80-c4c3-11eb-9226-04c5b063a5ee.PNG)

- Additional Setting

![addi_set](https://user-images.githubusercontent.com/60148173/120691134-b3d9e300-c4c3-11eb-838b-6d1ea317df13.PNG)

- Launch Database select *create Database*

- Database

![create_db](https://user-images.githubusercontent.com/60148173/120691455-1a5f0100-c4c4-11eb-8111-0ee4a85ee6d8.PNG)

## Select Next [Step3](configure_database.md)

