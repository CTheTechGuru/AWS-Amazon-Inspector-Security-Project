<h1 align="center">AWS Security | Amazon Inspector Project Lab</h3>

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/amazon_inspector-1600.jpg?raw=true)





<!-- PROJECT Details-->
### About The Project:

We will create a production environment for an EC2 instance which we will perform a network check for vulnerabilities. The tool we will use to perform the check is Amazon Inspector, which is a vulnerability management tool in AWS.
Amazon Inspector have quite a few benefits including the detection of software vulnerabilities, prioritize remediation reducing mean time to remediate (MTTR), and the ability to conduct agent based and agent-less scanning. 


#### Overview:
* We will create a target instance.
* Add a tag consisting of key | value tags to identify out instance.
* Install agent on target instance.
* Set Rules and scheduling for target assessment.
* Create template.
* Run Vulnerability Scanner.
* Review Findings. 



 #### Prerequisites:


* Basic understanding of AWS core services.
* Base level knowledge of cybersecurity terms and tools. 
* Access to AWS (Free Tier or Paid)
* Create AWS user account with administrator access. (enable MFA on lab account)
  
#### Fun Fact: 
* AWS has customers who use Amazon Inspector within their organization and its benefits vary from company to company. 

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Amazon%20Inspector%20Clients.PNG)

## Steps

### 1. Create EC2 Instance

* Go to EC2 Console and Launch Instance

* We will choose Amazon Linux (Free tier eligible)
* t2.micro (free tier eligible)
* Choose key pair or create as needed.
* Edit Network settings, Choose the default vpc, subnet 1a, and Enable Auto assign IP.

 
![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/EC2%20Instance.png?raw=true)

* Launch Instance
  
![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/2.png?raw=true)

* After Instance is launched go to main EC2 Dashboard and highlight the instance checkbox, in the lower panel choose manage tags.

![ Change Key Value to the corresponding](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/-.png?raw=true)

* While in the EC2 Dashboard, select the instance and below choose security
* Change Security Group inbound rule and enable port 21 and 23 which is ftp and telnet.
* These protocols aren't very secure and would allow our vulnerability scanner to pick up vulnerabilities.

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/FTP%20Telnet.png?raw=true)







### 2. Define Assessment Target

* Now we will go to Amazon Inspector.
  
![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Amazon%20Inspector.png)

* Choose the Get Started Tab. 
* Next choose Advanced Setup.
* Now we will define our assessment target.
* Give the assessment target a name and uncheck All Instances.
* Choose the Key and Value dropdowns to the corresponding ones made earlier during the EC2 creation.
* 
![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Assessment%20Target.png)

* Checkbox for Install Agents.
  
  

### 3. Define Assessment Template

* We will Give our template a name.
* For Rule Packages we will choose Network Reachability and Common Vulnerabilities and Exposures-1.1
* Set the duration for 15 minutes. 
* Uncheck the box for recurring Assessment Schedule.

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Prod%20Assessment.png?raw=true)




## 4. Run Amazon Inspector

* After Creating the Assessment Template you should return to the following screen below. Choose Run. 

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Amazon%20Inspector%20Findings.png?raw=true)

* After you choose run the scanner will proceed to analyze the instance for vulnerabilities and network reachability. 
* Select findings. 



 
## 5. Amazon Inspector Findings

* Under the Findings section, you will discover any vulnerabilities that surfaced during the scan.

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Amazon%20Inspector%20Findings.png?raw=true)


* The results will range from High, Low, Medium, based off severity. 

* Below is a display of port 21 and 23 analysis as both are /High on the severity list.

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Port%2021%20Analysis.png)

![](https://github.com/CTheTechGuru/AWS-Amazon-Inspector-Security-Project/blob/main/images/Port23%20Analysis.png)


* Note at the bottom of the findings you will see the severity, description as well as recommendation to remediate the sev.

<h1 align="center">Summary</h3>

There are endless use cases for Amazon Inspector. In traditional on premise environments the use of a third party vulnerability management tool is common. 
Being that more companies are transitioning to the cloud services like Amazon Inspector allows us to remediate vulnerabilities with an integrated service 
which is cost efficient and compliments a well architected framework ensuring a secure production environment. That wraps up this demonstration, 
If you followed along be sure to terminate all instances and delete targets within Amazon Inspector to avoid costs. Until next time. Peace!


<!-- CONTACT -->
## Contact

Cordelra Lowman - Cordelra_Lowman@yahoo.com

<h3 align="left">Follow me on Linkedin:</h3>
<p align="left">
<a href="https://linkedin.com/in/cordelra lowman" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="cordelra lowman" height="30" width="40" /></a>
</p>






