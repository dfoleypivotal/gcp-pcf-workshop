![](images/title.png)  
Update: September 5, 2018

## Introduction

This workshop will walk you through the process of deploying and monitoring an application on **Pivotal Cloud Foundry (PCF)**. PCF will be running on **Google Cloud Platform (GCP)** and you will get exposed how PCF consumes GCP services.

***To log issues***, click here to go to the [github](https://github.com/dfoleypivotal/gcp-pcf-workshop/issues) repository issue submission form.

## Objectives
- Install PCF on GCP using Quickstart
- Deploy an Application to PCF
- Understand how to Monitoring and Logging works in PCF
- Scale the number of instances of your application
- Understand High Availability capabilites of PCF platform
- Consume GCP Services from PCF application
- View PCF logs with GCP Stackdriver
- Understand how to do a Blue Green Deployment
- Setup Application Autoscaler

## Required Artifacts
- The following lab requires an Google Cloud Platform account.

## Create PCF platform on GCP using Quickstart.

### **STEP 1**: Open Cloud Shell
- From any browser, go to the URL to access Google Cloud Console:

   `https://console.cloud.google.com/`

- After you login to your GCP account click on Cloud Shell in the upper right hand corner.

    ![](images/image1.png)

- Cloud Shell will open in the bottom of your browser.

    ![](images/image2.png)

### **STEP 2**: Install PCF on GCP
- Open a new tab and go the following URL:

   `https://github.com/cf-platform-eng/gcp-pcf-quickstart`

- Follow the instruction for prerequisites, setup DNS and Deploy PCF

    ***Note:*** Throughout the document we will reference *`<yourdomain>`* as the DNS entry. Document will also assume that Cloud DNS was setup using *`pcf.<yourdomain>`*.

### **STEP 3**: Login to Pivotal Cloud Foundry

- From the PCF GCP Quickstart directory run the following command to get login information for Ops Manager:

    ```./util/env_info.sh opsman```

    ![](images/image3.png)

- From any browser, open a new tab and go to the URL to access Pivotal Ops Manager.  Use the username and password returned from the command above to login. 

    ![](images/image4.png)

- From the PCF GCP Quickstart directory run the following command to get login information for Apps Manager:

    ```./util/env_info.sh cf```

    ![](images/image5.png)

- From any browser, open a new tab and go to the URL:

   `https://apps.sys.pcf.<yourdomain>`

 - To access Pivotal Apps Manager.  Use the username and password returned from the command above to login. 

    ![](images/image6.png)

- Leave both Ops Manager and Apps Manager tabs open as we will be using them later in the lab.

- Now we want to target out CLI at our newly created environment. From Cloud Shell run the following commands to target and login to CF CLI. For ***Space*** selection hit Enter as we will create a new org and space for application deployment.

```
cf api https://api.sys.pcf.<yourdomian> --skip-ssl-validation
cf login -u admin -p <password from above>
```
![](images/image7.png)





