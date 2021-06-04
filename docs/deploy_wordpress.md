# Step 5: Deploy Wordpress

In this step, we will make our Apache web server handle requests for WordPress.

- First, install the application dependencies we need for WordPress. In our terminal, run the following command.
> sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2

![install-app_dep](https://user-images.githubusercontent.com/60148173/120820523-42a53900-c572-11eb-9e97-95ab75d9a844.PNG)


- Second, change to the proper directory by running the following command:
> cd /home/ec2-user

- Then, copy  WordPress application files into the /var/www/html directory used by Apache.
>sudo cp -r wordpress/* /var/www/html/

- Finally, restart the Apache web server to pick up the changes.
>sudo service httpd restart

![start_system](https://user-images.githubusercontent.com/60148173/120820663-5ea8da80-c572-11eb-8186-a09e0234f6e9.PNG)

- Now, we’re all done with the configurations. Open the WordPress application using localhost:<port>.So we can add the here  Database Name,UserName,Password,Database Host,and table Prefix
  
![webpage](https://user-images.githubusercontent.com/60148173/120821572-39689c00-c573-11eb-846c-b67c21eb6fcf.PNG)
  

That’s it. You have a live, publicly-accessible WordPress installation using a fully-managed MySQL database on Amazon RDS.
  
Thank You for Reviews this !!!!!!!!!!!!!!
