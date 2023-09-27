# Deploying-a-Honeypot-on-AWS
A honeypot is essentially a system that mimics a vulnerable target to entice attackers. These systems do not, at least they shouldn’t, have any valuable information. Instead, they are configured to thoroughly log what an attacker is doing to gain insight into attacks and techniques.


**AWS:**
The honeypot works best on the cloud since it is convenient, rapid, and inexpensive. Many cloud service providers provide a free tier with a free virtual machine or credit to use for cloud resources.
Click Launch instance on the EC2 Dashboard. This will begin the process of setting up a virtual machine.

![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/0dc164a9-5aed-432f-b741-3b1449359fd2)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/7cdab273-03e8-49dd-a570-6144b4a7066f)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/f51dd623-b8ff-43ca-8f8e-624d3c742a6f)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/9e5320b9-750b-4aad-8f74-a3f01eb5dbfc) 

The instance will take a short time to boot. You will then see a lot of information about the machine, which includes its public IPv4 address. This is the address that will be used to reach the services set up:
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/2c7f0306-bbea-4694-a168-86428e9184af)


**Connect to your EC2 Instance:**
Now it’s time to SSH onto the instance and run an update on it. The easy way to do this is to go back to the instance we created in AWS and click on the Instance ID of our created instance. This will bring you to another page with information on our instance. Click Connect at the top right. Next, we’ll see another page with information under SSH Client. This is giving you information on how to SSH into the instance. We’ll see something that says with a command string that we’ll use to SSH into your instance in the command line.

![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/25540789-dd65-4fad-8e94-fa917d9c7749)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/756b5e32-b93e-4076-9352-0c80b190d111)

**T-Pot Installation**
We’ll be downloading T-Pot from github.com: sudo git clone https://github.com/telekom-security/tpotce.git. Now running ls we’ll see we now have a directory called tpotce. Once you see this directory cd into it and run this install script: sudo ./install.sh — type=user. This install process may take a while. Once a prompt comes up for yes or no type y.

![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/2e1d3e8f-fa6f-484f-82b7-6b0e9d2c3490)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/59c67797-ff1b-4413-bd1e-a362ea6cb1a3)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/4460229c-8f44-473b-b636-3cb97bda9055)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/4809217e-9cfe-4b99-819a-b3c4485cdd08)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/e16c9f80-f5ca-43ad-983d-59f4f54a7630)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/828e3295-1a3c-4a1e-8b3a-51c5921c43e1)

**Security Groups**
This process will end up changing the ports associated with your instance for ssh and the website. We’ll need to go back to AWS and change the security group rules for the honeypot instance. Once back on the instance page in AWS scroll towards the bottom and click on security. Then click on the hyperlink under the security groups Tab.
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/2bbc5b27-03e5-43c2-bba4-c4a96c4a0626)

On the next page scroll to the bottom and click on Edit Inbound Rules. Here we will change the rules for ssh to the instance as well as the website. Port 64295 is for ssh and Port 64297 is for the website.

![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/fc0cdea2-708c-4766-b7d4-00fa8c7956c7)

**T-Pot Admin Portal**

Now it’s time to go to our internet browser and type log into the web admin portal for our T-Pot. In the browser URL bar type https://{our public IP address from AWS). If there are security settings on your browser then just click advanced and proceed to the IP address. This is where it’s important that you saved those credentials earlier. Enter the credentials and we'll be taken to the T-Pot web admin portal.
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/15f0b755-a91b-4852-a67c-91b5675c89d4)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/e587e6a0-e749-422e-bc1d-fe509bbff298)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/e487876b-a422-4ddb-b863-fd3b3394def5)
![image](https://github.com/bivin-88/Deploying-a-Honeypot-on-AWS/assets/80203330/96a0b386-2f91-47af-a5fe-b780861581f4)

Using T-Pot can be beneficial for you to learn to use OSINT for various attacks and to see what a specific IP address is up to.
T-Pot’s visualizations on the number of attacks are quite astounding. Seeing the different attack types and origin of attack should instill in all of us that attackers are trying to get into our systems.







 
 
 
 


 

 
 
 
 


 


