## Capstone Project: E-commerce Platform Deployment with Git, Linux, and AWS

**Project Instructions**

In this project I will be developing an e-commerce website for a new online marketplace named "MarketPeak." This platform will feature product listings, a shopping cart, and user authentication. I will implement this project by using Git for version control, i will develop the platform in a Linux environment, and deploy it on an AWS EC2 instance.

## Tasks 1: Implement Version Control with Git

**1.1.  Initialize Git Repository:** Create the project directory and name it "MarketPeak_Ecommerce". then cd into the new project directory and initialize a git repository.

```markdown
mkdir MarketPeak_Ecommerce
cd MarketPeak_Ecommerce
git init
```

**1.2. Obtain and Prepare the E-Commerce Website Template:** 
Instead of developing the website from scratch, I used a pre-existing e-commerce website template as the actual website is usually done by web/software developers.

**1.3 Download a Website Template:** Visit (Tooplate)[https://www.tooplate.com/] or any other free template resource. Look for templates that are ready to use and require minimal adjustments.

**1.4 Prepare the Website Template:** Extract the downloaded template into your project directory, MarketPeak_Ecommerce

**1.5 Stage and Commit the Template to Git:** I added the website files, setup Git configuration, and commit the changes to the MarketPeak_Ecommerce Git repository with the command

```
git add .
git config --global user.name "YourUsername"
git config --global user.email "youremail@example.com"
git commit -m "Initial commit with basic e-commerce site structure"
```

**1.6 Create a remote Github repository:** I proceeded to create a repository on Github and named it Market_Peak_Ecommerce

**1.7 Link Local Repository to Github:** On my terminal, i navigated to the project directory and cloned the remote repository URL to the local repository
```
git remote add origin https://github.com/Aded0yin/MarketPeak_Ecommerce.git
```

**1.7 Push the code to Github repository:** I pushed the code using the following command

```
git push -u origin main
```

## Step 2: AWS Deployment

**Task 1: Setup an AWS EC2 instance for deployment**

* I logged in to the AWS Management Console.
* I launched an EC2 instance using an Amazon Linux AMI.
* I connected to the instance using Https
* I then proceeded to clone the Github repository to my AWS EC2 instance with the following command

```
git clone https://github.com/Aded0yin/MarketPeak_Ecommerce.git
```

** Installing a web server on EC2**

Apache HTTP Server (httpd) is a widely used web server that serves HTML files over the internet. Installing it on Linux EC2 server will allow me to host the MarketPeak E-commerce site: Note that httpd is the software name for Apache on redhats systems using yum package manager

I then proceeded to install Apache web server on my EC2 instance using the following commands

```
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

```

- Prepare the web directory: I configured httpd for the website with the next command

  ```
  sudo rm -rf /var/www/html/*
  sudo cp -r ~/MarketPeak_Ecommerce/2137_barista_cafe/* /var/www/html/

  ```

- Reload httpd: I applied changes by reloading the httpd service

```
sudo systemctl reload httpd

```

- Access Website from Browser: After i configured httpd and website files intact, i proceeded to open my web browser to access MarketPeak_Ecommerce with the public IP of my EC2 instance. I could not view the web page initially until i opened the port in the AWS security group.


## Step 3: Continuous Integration and Deployment Workflow



