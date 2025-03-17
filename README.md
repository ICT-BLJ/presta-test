# PrestaShop Docker Installation Guide

## Introduction
This repository provides a ready-to-use Docker setup for PrestaShop with MySQL. Follow the steps below to clone the repository and initialize PrestaShop with predefined settings.

## Prerequisites
- Docker
- Docker Compose

## Installation Steps

### 1. Clone the Repository
```sh
git clone <your-repository-url>
cd <your-repository-folder>
```

### 2. Start the Docker Containers
```sh
docker-compose up -d
```
This will start MySQL and PrestaShop containers.

### 3. Initialize PrestaShop
Once the containers are running, open a web browser and go to:
```
http://localhost:8080
```
Follow the installation steps with the predefined values:

#### **Step 1: License Agreement**
- Accept the Terms and Conditions

#### **Step 2: Shop Information**
- **Shop Name:** ZLI TestShop
- **Activity:** Other
- **Country:** Switzerland
- **Enable SSL:** No

#### **Step 3: Your Account**
- **First Name:** ZLI
- **Last Name:** Admin
- **Email:** test@zli-testshop.ch
- **Password:** Zli_12345!

#### **Step 4: Database Configuration**
- **Database Server Address:** db
- **Database Name:** prestashop
- **Database User:** prestashop
- **Database Password:** prestashop
- **Table Prefix:** ps_
- **Drop Existing Tables:** Checked

### 4. Complete Installation
Click on **Install** and wait for the process to complete.

### 5. Remove the Installation Folder
After the installation, remove the `install` folder inside the PrestaShop container to prevent security risks:
```sh
docker exec -it prestashop_app rm -rf /var/www/html/install
```

### 6. Access the Admin Panel
Once the installation is complete, access the admin panel:
```
http://localhost:8080/admin
```
Login with the credentials set during installation:
- **Email:** test@zli-testshop.ch
- **Password:** Zli_12345!

## Notes
- If you encounter database connection issues, ensure MySQL is running properly by checking logs:
```sh
docker logs prestashop_db
```
- Restart the setup if needed:
```sh
docker-compose down -v && docker-compose up -d
```

Enjoy your PrestaShop installation! 🚀