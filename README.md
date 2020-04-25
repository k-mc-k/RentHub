# RentHub
Deploy RentHub on your own Server

### Prerequisites
* RentHub zip folder of all application files
* PHP 7.2 and MySQL 5.7 installed on your server

### Deployment
In order to run RentHub on your sever, there are 4 files you will need to update with your own configuration details - config.php, landlord-index.php, tenant-index.php & tenant-new.php

```
            $server = 'localhost';
            $username = 'user';
            $password = 'password';
            $database = 'renthub';
```

Also, make sure you have created a database named 'renthub' that contains 3 tables - tenants, landlords & comments.

#### Tenants
```
CREATE TABLE tenants (
tenant_id INT PRIMARY KEY AUTO_INCREMENT,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
phone_number VARCHAR(50) NOT NULL,
email_address VARCHAR(75) NOT NULL,
account_password VARCHAR(100) NOT NULL,
member_since TIMESTAMP,
profile_picture VARCHAR(150),
num_adults INT(11),
num_children INT(11),
pets BOOLEAN,
pet_desc VARCHAR(200),
smoker BOOLEAN,
bedrooms INT(11),
rental_type VARCHAR(100),
city VARCHAR(50),
profile_active BOOLEAN,
birthday VARCHAR(15),
monthly_rent VARCHAR(30),
tenant_about TEXT
);
```

#### Landlords
```
CREATE TABLE landlords (
landlord_id INT PRIMARY KEY AUTO_INCREMENT,
f_name VARCHAR(50) NOT NULL,
l_name VARCHAR(50) NOT NULL,
city VARCHAR(50),
province VARCHAR(10),
email_address VARCHAR(75) NOT NULL,
account_password VARCHAR(100) NOT NULL,
member_since TIMESTAMP
);
```

#### Comments
```
CREATE TABLE comments (
comment_id INT PRIMARY KEY AUTO_INCREMENT,
tenant_id INT(11)
landlord_id INT(11)
comment TEXT,
date TIMESTAMP
);
```
