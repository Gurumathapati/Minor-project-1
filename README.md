# AWS EC2 + S3 + Nginx Minor Project

## Project Overview

This project demonstrates how to deploy and host a
static website using Amazon EC2 and Nginx Web Server,
with Amazon S3 used for website backup storage.

## Technologies Used

- Amazon Web Services (AWS)
- Amazon EC2
- Amazon S3
- Amazon Linux 2023
- Nginx Web Server
- HTML and CSS
- SSH
- Linux

## Project Architecture

```text
           User / Browser
                 |
                 | HTTP (Port 80)
                 |
                 v
          Amazon EC2 Instance
          (Amazon Linux 2023)
                 |
                 v
           Nginx Web Server
                 |
                 v
              index.html

          Website Backup
                 |
                 v
             Amazon S3
```

## Implementation Steps

### Step 1: Launch EC2 Instance

- Launched an Amazon Linux 2023 EC2 instance.
- Selected the t2.micro instance type.
- Configured SSH (22) and HTTP (80) inbound rules.
- Created an SSH key pair.

### Step 2: Connect to EC2

Connected to the EC2 instance using SSH.

### Step 3: Install Nginx

```bash
sudo dnf update -y
sudo dnf install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

Verify Nginx:

```bash
sudo systemctl status nginx
```

### Step 4: Deploy Static Website

Created the website at:

```text
/usr/share/nginx/html/index.html
```

Verified the website using the EC2 public IP address.

### Step 5: Create Amazon S3 Bucket

- Created an S3 bucket.
- Kept public access blocked.
- Uploaded the website backup file.
- Verified the uploaded object.

## Project Structure

```text
AWS-EC2-S3-Nginx-Minor-Project/
├── README.md
├── website/
│   └── index.html
├── screenshots/
└── docs/
```

## Screenshots

### EC2 Instance
![EC2 Instance](screenshots/01-EC2-Instance.png)

### Security Group
![Security Group](screenshots/02-Security-Group.png)

### Nginx Website
![Nginx Website](screenshots/03-Nginx-Website.png)

### S3 Bucket
![S3 Bucket](screenshots/04-S3-Bucket.png)

### S3 Uploaded Files
![S3 Uploaded Files](screenshots/05-S3-Uploaded-Files.png)

## Learning Outcomes

- Launching and configuring Amazon EC2 instances.
- Connecting securely to Linux servers using SSH.
- Installing and managing Nginx.
- Hosting static websites on cloud infrastructure.
- Configuring security groups.
- Creating S3 buckets and uploading backup files.
## Deployment Details

| Configuration | Details |
|---|---|
| Cloud Provider | AWS |
| Compute Service | Amazon EC2 |
| Operating System | Amazon Linux 2023 |
| Instance Type | t2.micro |
| Web Server | Nginx |
| Website | HTML & CSS |
| Storage Service | Amazon S3 |
| Protocol | HTTP |
| Port | 80 |
| Deployment Status | Successfully Deployed |

## Live Demo

[Visit My AWS Cloud Project](http://3.26.158.246/)

> **Note:** The live website is accessible only while
> the EC2 instance is running and its public IP remains
> assigned. The source code and screenshots are
> available in this GitHub repository.
## Conclusion

Successfully deployed a static HTML website on
Amazon EC2 using Nginx and stored website backup
files in Amazon S3.
