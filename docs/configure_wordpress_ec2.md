# Step 4: Configure Wordpress On EC2

In this step we Install the WordPress application and dependencies on the EC2 instance

## Installing the Apache Web Server
To run WordPress, we need to run a web server on our EC2 instance. The open source Apache web server is the most popular web server used with WordPress.
- To install Apache on EC2 instance, run the following command in terminal:
> sudo yum install -y httpd

- To start the Apache web server, run the following command in terminal:

![start_system](https://user-images.githubusercontent.com/60148173/120814848-e390f580-c56c-11eb-80d9-99e19c150f3b.PNG)

- Then check the Status of Apache service so to run the following command in terminal:
> systemctl status httpd

![start_httpd](https://user-images.githubusercontent.com/60148173/120815186-38cd0700-c56d-11eb-98a6-ecfd3254e87a.PNG)

Now that your Apache web server is working, it’s time to download and configure WordPress.

## Download Wordpress on EC2 instance
In this step, we will download the WordPress software and set up the configuration.

- First, download and uncompress the software by running the following commands in terminal:
```
wget https://wordpress.org/latest.tar.gz
tar -xzf latest.tar.gz
```
![download_wordpress](https://user-images.githubusercontent.com/60148173/120816568-7f6f3100-c56e-11eb-93e0-70ec89d0d9bf.PNG)

- if ls command run in terminal then it show in directory wordpress with the uncompressed contents.
```
$ ls
latest.tar.gz  wordpress
```
- Change into the wordpress directory and create a copy of the default config file using the following commands:
```
cd wordpress
cp wp-config-sample.php wp-config.php
```
- Then, open the wp-config.php file using the nano editor by running the following command.
>nano wp-config.php
![config_wordpress_mysql](https://user-images.githubusercontent.com/60148173/120817838-abd77d00-c56f-11eb-8b40-f7fe3ee9c48e.PNG)

- We need to edit two areas of configuration.
- First, edit the database configuration by changing the following lines:
```
// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define( 'DB_NAME', 'database_name_here' );

/** MySQL database username */
define( 'DB_USER', 'username_here' );

/** MySQL database password */
define( 'DB_PASSWORD', 'password_here' );

/** MySQL hostname */
define( 'DB_HOST', 'localhost' );
```
The values should be:

1. DB_NAME: “wordpressdb”
2. DB_USER: The name of the user that we created in the database in the previous module
3. DB_PASSWORD: The password for the user that created in the previous module.
4. DB_HOST: The hostname is the database Endpoint.

- The second configuration section we need to configure is the Authentication Unique Keys and Salts. It looks as follows in the configuration file:
```
/**#@+
 * Authentication Unique Keys and Salts.
 *
 * Change these to different unique phrases!
 * You can generate these using the {@link https://api.wordpress.org/secret-key/1.1/salt/ WordPress.org secret-key service}
 * You can change these at any point in time to invalidate all existing cookies. This will force all users to have to log in again.
 *
 * @since 2.6.0
 */
define( 'AUTH_KEY',         'put your unique phrase here' );
define( 'SECURE_AUTH_KEY',  'put your unique phrase here' );
define( 'LOGGED_IN_KEY',    'put your unique phrase here' );
define( 'NONCE_KEY',        'put your unique phrase here' );
define( 'AUTH_SALT',        'put your unique phrase here' );
define( 'SECURE_AUTH_SALT', 'put your unique phrase here' );
define( 'LOGGED_IN_SALT',   'put your unique phrase here' );
define( 'NONCE_SALT',       'put your unique phrase here' );
```
![config_wordpress_mysql2](https://user-images.githubusercontent.com/60148173/120818925-ae86a200-c570-11eb-8d65-16aea55b6d0d.PNG)

With the configuration updated, we are almost ready to deploy our WordPress site. In the next step, we deploy the wordpress configuration Select [Step5](deploy_wordpress.md)

