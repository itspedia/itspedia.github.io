---
# Common-Defined
title: "Build a Resilient, Asynchronous System with Cloud Run and Pub/Sub"
date: 2025-03-22T21:20:23+08:00
lastmod: 2025-03-22T21:29:20+00:00
draft: false
tags: ["GCP", "Cloud Run", "Cloud Pub/Sub"]
categories: ["index", "GCP"]
author: "hongxing"

# User-Defined
# You can close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: false
# You can also define another contentCopyright
contentCopyright: '<a rel="license noopener" href="https://creativecommons.org/licenses/by-nc-nd/4.0/" target="_blank">CC BY-NC-ND 4.0</a>'
reward: false
mathjax: true
---
# GSP650-Build a Resilient, Asynchronous System with Cloud Run and Pub/Sub

## GSP650

![Google Cloud self-paced labs logo](https://cdn.qwiklabs.com/GMOHykaqmlTHiqEeQXTySaMXYPHeIvaqa2qHEzw6Occ%3D)

![Pet Theory logo](https://cdn.qwiklabs.com/o9xaY3ombOkGaC1vyR%2FKpl5TOGCpl1oBSHXLG3SkFbU%3D)

## Overview

For the labs in the [Serverless Cloud Run Development](https://www.cloudskillsboost.google/course_templates/741) course, you will read through a fictitious business scenario and assist the characters with their serverless migration plan.

Twelve years ago, Lily started the Pet Theory chain of veterinary clinics. Over the years, the number of clinics has grown, and so has the need for automation. The way Pet Theory handles the results of medical tests when they come back from the lab is too slow and error-prone, and Lily wants to improve this.

Currently, Patrick, Pet Theory's IT administrator, handles test results manually. Whenever a test result comes back, he composes and sends an email to the client whose pet was tested, then he taps out a text message on his phone and sends the results as a text to the client.

Patrick is working with Ruby, a software consultant, to design a more scalable system. They want to build a solution that doesn't require a lot of ongoing maintenance. Patrick and Ruby have decided to go with serverless technology.

## Objectives

In this lab, you will learn how to:

- Create a Pub/Sub topic and subscription
- Create a Cloud Run service that receives HTTP requests and publishes messages to Cloud Pub/Sub
- Create a Cloud Run service that receives messages from Cloud Pub/Sub
- Create a Pub/Sub subscription that triggers a Cloud Run service
- Test the resiliency of a system

### Prerequisites

This lab assumes familiarity with the Cloud Console and shell environments. This lab is part of a series. Taking the previous labs could be helpful, but is not necessary:

- [Importing Data to a Firestore Database](https://google.qwiklabs.com/catalog_lab/2163)
- [Build a Serverless Web App with Firebase](https://google.qwiklabs.com/catalog_lab/2166)
- [Build a Serverless App with Cloud Run that Creates PDF Files](https://google.qwiklabs.com/catalog_lab/2161)

## Setup and requirements

**Note:** For this lab, sign in into the Google Cloud Console as Username 1. Otherwise, you will encounter errors during the lab.

### Before you click the Start Lab button

Read these instructions. Labs are timed and you cannot pause them. The timer, which starts when you click **Start Lab**, shows how long Google Cloud resources are made available to you.

This hands-on lab lets you do the lab activities in a real cloud environment, not in a simulation or demo environment. It does so by giving you new, temporary credentials you use to sign in and access Google Cloud for the duration of the lab.

To complete this lab, you need:

- Access to a standard internet browser (Chrome browser recommended).

**Note:** Use an Incognito (recommended) or private browser window to run this lab. This prevents conflicts between your personal account and the student account, which may cause extra charges incurred to your personal account.

- Time to complete the lab—remember, once you start, you cannot pause a lab.

**Note:** Use only the student account for this lab. If you use a different Google Cloud account, you may incur charges to that account.

### How to start your lab and sign in to the Google Cloud console

1. Click the **Start Lab** button. If you need to pay for the lab, a dialog opens for you to select your payment method. On the left is the Lab Details pane with the following:

   - The Open Google Cloud console button
   - Time remaining
   - The temporary credentials that you must use for this lab
   - Other information, if needed, to step through this lab

2. Click **Open Google Cloud console** (or right-click and select **Open Link in Incognito Window** if you are running the Chrome browser).

   The lab spins up resources, and then opens another tab that shows the Sign in page.

   ***Tip:\*** Arrange the tabs in separate windows, side-by-side.

   **Note:** If you see the **Choose an account** dialog, click **Use Another Account**.

3. If necessary, copy the **Username** below and paste it into the **Sign in** dialog.

   ```
   student-03-8c7b2c03a5b3@qwiklabs.net
   ```

   

   You can also find the Username in the Lab Details pane.

4. Click **Next**.

5. Copy the **Password** below and paste it into the **Welcome** dialog.

   ```
   Qgnf7gsvUwCY
   ```

   

   You can also find the Password in the Lab Details pane.

6. Click **Next**.

   **Important:** You must use the credentials the lab provides you. Do not use your Google Cloud account credentials.

   **Note:** Using your own Google Cloud account for this lab may incur extra charges.

7. Click through the subsequent pages:

   - Accept the terms and conditions.
   - Do not add recovery options or two-factor authentication (because this is a temporary account).
   - Do not sign up for free trials.

After a few moments, the Google Cloud console opens in this tab.

**Note:** To access Google Cloud products and services, click the **Navigation menu** or type the service or product name in the **Search** field. ![Navigation menu icon and Search field](https://cdn.qwiklabs.com/9Fk8NYFp3quE9mF%2FilWF6%2FlXY9OUBi3UWtb2Ne4uXNU%3D)

### Activate Cloud Shell

Cloud Shell is a virtual machine that is loaded with development tools. It offers a persistent 5GB home directory and runs on the Google Cloud. Cloud Shell provides command-line access to your Google Cloud resources.

1. Click **Activate Cloud Shell** ![Activate Cloud Shell icon](https://cdn.qwiklabs.com/ep8HmqYGdD%2FkUncAAYpV47OYoHwC8%2Bg0WK%2F8sidHquE%3D) at the top of the Google Cloud console.
2. Click through the following windows:
   - Continue through the Cloud Shell information window.
   - Authorize Cloud Shell to use your credentials to make Google Cloud API calls.

When you are connected, you are already authenticated, and the project is set to your **Project_ID**, `qwiklabs-gcp-03-11a04fa27be6`. The output contains a line that declares the **Project_ID** for this session:

```
Your Cloud Platform project in this session is set to qwiklabs-gcp-03-11a04fa27be6
```

`gcloud` is the command-line tool for Google Cloud. It comes pre-installed on Cloud Shell and supports tab-completion.

3. (Optional) You can list the active account name with this command:

```
gcloud auth list
```



4. Click **Authorize**.

**Output:**

```
ACTIVE: *
ACCOUNT: student-03-8c7b2c03a5b3@qwiklabs.net

To set the active account, run:
    $ gcloud config set account `ACCOUNT`
```

5. (Optional) You can list the project ID with this command:

```
gcloud config list project
```



**Output:**

```
[core]
project = qwiklabs-gcp-03-11a04fa27be6
```

**Note:** For full documentation of `gcloud`, in Google Cloud, refer to [the gcloud CLI overview guide](https://cloud.google.com/sdk/gcloud).

### Set your region and zone

Certain Compute Engine resources live in regions and zones. A region is a specific geographical location where you can run your resources. Each region has one or more zones.

**Note**: Learn more about regions and zones and see a complete list in [Regions & Zones documentation](https://cloud.google.com/compute/docs/regions-zones/).

Run the following gcloud commands in Cloud Shell to set the default region and zone for your lab:

```
gcloud config set compute/zone "us-east1-d"
export ZONE=$(gcloud config get compute/zone)

gcloud config set compute/region "us-east1"
export REGION=$(gcloud config get compute/region)
```



### Scenario

Pet Theory would like to automate the process of sharing client test results. They have experienced a tough time keeping up with an increased volume of appointments, so Lily decides to ask Ruby for some assistance...

| ![Lily](https://cdn.qwiklabs.com/SAe6MsJi2voh0ygak%2BAV2SzyXCCtjirn9cKOaQV2nU4%3D)*Lily, Founder of Pet Theory* | Hi Ruby,Thanks for sorting out the insurance portal.I was wondering if something could be done about the medical test results? We need a more efficient way of sending results to our clients.Lily |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Ruby](https://cdn.qwiklabs.com/Gwp1lYw8XYLWIik3Af6zvmninmjnf%2B9%2BzTzDK92kuOc%3D)*Ruby, Software Consultant* | Hey Lily,Sure - let me see what I can do. I have a few ideas that may improve the situation.Ruby |

## Task 1. Architecture

Pet Theory uses an external company for medical tests. Once the lab company completes a medical test, they send the results back to Pet Theory.

The lab company uses a HTTP(s) POST to Pet Theory's web endpoint for medical lab results. The illustration below outlines the general architecture.

![Pet Theory's system architecture diagram](https://cdn.qwiklabs.com/6J7PDgV%2FpYo00ESDhV5JBl2G%2FvpEZ0LYsOre9WF9zfk%3D)

After looking at the general process followed, Ruby believes that a system can be designed in which Pet Theory is able to:

1. Receive the HTTP POST request and confirm receipt to the medical lab.
2. Email the test result to the client.
3. Send a text message (SMS) and an email to the client with the test result.

Ruby's design isolates each of the above activities and requires:

- A service to perform the request and response for the medical result(s)
- A service to email test results to the client
- A service to send a text message (SMS) to the client
- Pub/Sub to be used for inter-service communication
- Serverless infrastructure to be used for the application architecture

Through the use of single use functions, Ruby is looking to develop code that is easier to write and contains fewer bugs.

| ![Ruby](https://cdn.qwiklabs.com/Gwp1lYw8XYLWIik3Af6zvmninmjnf%2B9%2BzTzDK92kuOc%3D)*Ruby, Software Consultant* | Hi Patrick,Lily would like me to build a prototype to help with the processing of medical records.To get started, could you set up a Pub/Sub Topic called `new-lab-report`.Ruby |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Patrick](https://cdn.qwiklabs.com/Nv72Ggsv1sii%2FIlvLOvmvD5Q0DapYPH1LIJJhECeNsE%3D)*Patrick, IT Administrator* | Hey Ruby,That sounds like a cool project. I can get that finished for you this morning, both activities are really quick to set up on Google Cloud.Patrick |

### **Create a Pub/Sub topic**

Help Patrick to create a Pub/Sub topic called `new-lab-report`.

![Cloud Pub/Sub highlighted in architecture diagram](https://cdn.qwiklabs.com/%2BsXFeTs902rTTPxNT%2BRV39seRaOvufAewh1VJpc%2B7Oc%3D)

When a service publishes a Pub/Sub message, that message must be tagged with a topic. The Lab Report is consumed via the service to be created and publish a message for each report found.

First you need to create a topic that can be used for this task.

1. Run the following command to create a Pub/Sub topic:

```
gcloud pubsub topics create new-lab-report
```



Any service subscribed to the topic "new-lab-report" will be able to consume the message published by the Lab Report Service. In the above diagram you can see two such consumers, Email Service and SMS Service.

2. Then enable Cloud Run, which will run your code in the cloud:

```
gcloud services enable run.googleapis.com
```



Don't forget to update Ruby to let her know that the Pub/Sub topic is ready for her!

| ![Patrick](https://cdn.qwiklabs.com/Nv72Ggsv1sii%2FIlvLOvmvD5Q0DapYPH1LIJJhECeNsE%3D)*Patrick, IT Administrator* | Hey Ruby,All done.If you have time, I would like to see how this prototype is put together. Could we work on this together?Patrick |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Ruby](https://cdn.qwiklabs.com/Gwp1lYw8XYLWIik3Af6zvmninmjnf%2B9%2BzTzDK92kuOc%3D)*Ruby, Software Consultant* | Hi Patrick,That's great, thanks for getting to this so quickly. I'll set up a time and we'll start building.Ruby |

## Task 2. Build the Lab Report Service

Help Ruby to set up the new Lab Report Service.

![Lab Report Service highlighted in the architecture diagram](https://cdn.qwiklabs.com/iK4%2FDyuKKIVfMd6L1I8uZ%2BtwNHVrhsUZDjoSSfD5wZ4%3D)

This service will serve the purpose of prototyping, so it will only do two things:

1. Receive the lab report HTTPS POST containing the report data.
2. Publish a message on Pub/Sub.

### Add code for the Lab Report Service

1. Back in Cloud Shell, clone the repository needed for this lab:

```
git clone https://github.com/rosera/pet-theory.git
```



2. Move to the `lab-service` directory:

```
cd pet-theory/lab05/lab-service
```



3. Install the following packages that will be needed to receive incoming HTTPS requests and publish to Pub/Sub:

```
npm install express
npm install body-parser
npm install @google-cloud/pubsub
```



These commands update the `package.json` file to indicate the dependencies required for this service.

You will now edit the `package.json` file so that Cloud Run knows how to start your code.

4. Open the `package.json` file.

5. In the "scripts" section of the `package.json` file, add the code line `"start": "node index.js",` at line 7 (as shown below), and then save the file:

```
  "scripts": {
    "start": "node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```



**Note:** Be sure to add the code exactly as provided, including the ending comma:



```
"start": "node index.js",
```



Otherwise, you will encounter errors during deployment.

6. Create a new file named `index.js` and add this code to it:

```
const {PubSub} = require('@google-cloud/pubsub');
const pubsub = new PubSub();
const express = require('express');
const app = express();
const bodyParser = require('body-parser');
app.use(bodyParser.json());
const port = process.env.PORT || 8080;

app.listen(port, () => {
  console.log('Listening on port', port);
});

app.post('/', async (req, res) => {
  try {
    const labReport = req.body;
    await publishPubSubMessage(labReport);
    res.status(204).send();
  }
  catch (ex) {
    console.log(ex);
    res.status(500).send(ex);
  }
})

async function publishPubSubMessage(labReport) {
  const buffer = Buffer.from(JSON.stringify(labReport));
  await pubsub.topic('new-lab-report').publish(buffer);
}
```



These two lines do the main work of the service:



```
const labReport = req.body;
```



```
await publishPubSubMessage(labReport);
```



Specifically, these lines:

- Extract the lab report from the POST request.
- Publish a PubSub message containing the newly posted lab report.

7. Now create a file named `Dockerfile` and add the code below into it:

```
FROM node:18
WORKDIR /usr/src/app
COPY package.json package*.json ./
RUN npm install --only=production
COPY . .
CMD [ "npm", "start" ]
```



This file defines how to package up the Cloud Run service into a container.

### Deploy the lab-report-service

1. Create a file named `deploy.sh` and paste these commands into it:

```
gcloud builds submit \
  --tag gcr.io/$GOOGLE_CLOUD_PROJECT/lab-report-service
gcloud run deploy lab-report-service \
  --image gcr.io/$GOOGLE_CLOUD_PROJECT/lab-report-service \
  --platform managed \
  --region us-east1 \
  --allow-unauthenticated \
  --max-instances=1
```



2. In Cloud Shell, run the following to make this file executable:

```
chmod u+x deploy.sh
```



3. It's time to deploy the Lab Report Service! Run the deployment script:

```
./deploy.sh
```



Due to timing issues, you may get an error the first time you run this command. If you do, simply rerun `deploy.sh`.

When the deployment has successfully completed, you will see a message similar to this:

```
Service [lab-report-service] revision [lab-report-service-00001] has been deployed and is serving traffic at https://lab-report-service-[hash].a.run.app
```

Nice work, the Lab Report Service has been deployed and will consume medical lab results over HTTP. You can now test if the new service is up and running.

### Test the Lab Report Service

To validate the Lab Report Service, simulate three HTTPS POSTs made by the lab company, each containing one lab report. For the purpose of testing, the lab reports created will only contain an ID.

1. First, put the URL to the report in an environment variable, to make it easier to work with.

```
export LAB_REPORT_SERVICE_URL=$(gcloud run services describe lab-report-service --platform managed --region us-east1 --format="value(status.address.url)")
```



2. Confirm the LAB_REPORT_SERVICE_URL has been captured:

```
echo $LAB_REPORT_SERVICE_URL
```



3. Create a new file named `post-reports.sh` and add the code below into it:

```
curl -X POST \
  -H "Content-Type: application/json" \
  -d "{\"id\": 12}" \
  $LAB_REPORT_SERVICE_URL &
curl -X POST \
  -H "Content-Type: application/json" \
  -d "{\"id\": 34}" \
  $LAB_REPORT_SERVICE_URL &
curl -X POST \
  -H "Content-Type: application/json" \
  -d "{\"id\": 56}" \
  $LAB_REPORT_SERVICE_URL &
```



The above script will use the `curl` command to post three distinct ID's to the Lab Service URL. Each command will be run individually in the background.

4. Make the `post-reports.sh` script executable:

```
chmod u+x post-reports.sh
```



5. Now test the Lab Report Service endpoint by posting three lab reports to it using the script outlined above:

```
./post-reports.sh
```



This script posted three lab reports to your Lab Report Service. Check the logs to see the results!

1. In the Cloud console, click **Navigation menu (![Navigation menu icon](https://cdn.qwiklabs.com/tkgw1TDgj4Q%2BYKQUW4jUFd0O5OEKlUMBRYbhlCrF0WY%3D)) > Cloud Run**.
2. You should now see your newly deployed **lab-report-service** in the **Services** list. Click it.
3. The next page shows details about your lab-report-service. Click the **Logs** tab.

On the Logs page are the results of the three test reports that you just posted with the script. Hopefully the returned HTTP codes are 204, meaning OK - not content, shown below. If you don’t see any entries, try scrolling up and down using the scrollbar to the right. This reloads the log.

The next task is to write the SMS and Email services. These services will be triggered when the Lab Report Service publishes a Pub/Sub message on the "new-lab-report" topic.

## Task 3. The Email Service

Help Ruby to set up the new Email Service.

![Email Service highglighted in the architecture diagram](https://cdn.qwiklabs.com/orzDpUvALUCJSunp36E31dAwKyUFOub526r%2FLbjgOco%3D)

### Add code for the Email Service

1. Move to the Email Service directory:

```
cd ~/pet-theory/lab05/email-service
```



2. Install these packages so that the code can handle incoming HTTPS requests:

```
npm install express
npm install body-parser
```



The above command will update the `package.json` file, which describes the app and its dependencies. Cloud Run needs to know how to run the code, so add `start` instruction so that it knows what to do.

3. Open the `package.json` file.

4. In the "scripts" section, add the `"start": "node index.js",` line as shown below and save the file:

```
  "scripts": {
    "start": "node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```



**Note:** Be sure to add the code exactly as provided, including the ending comma:



```
"start": "node index.js",
```



Otherwise, you will encounter errors during deployment.

5. Create a new file called `index.js` and add the following to it:

```
const express = require('express');
const app = express();
const bodyParser = require('body-parser');
app.use(bodyParser.json());

const port = process.env.PORT || 8080;
app.listen(port, () => {
  console.log('Listening on port', port);
});

app.post('/', async (req, res) => {
  const labReport = decodeBase64Json(req.body.message.data);
  try {
    console.log(`Email Service: Report ${labReport.id} trying...`);
    sendEmail();
    console.log(`Email Service: Report ${labReport.id} success :-)`);
    res.status(204).send();
  }
  catch (ex) {
    console.log(`Email Service: Report ${labReport.id} failure: ${ex}`);
    res.status(500).send();
  }
})

function decodeBase64Json(data) {
  return JSON.parse(Buffer.from(data, 'base64').toString());
}

function sendEmail() {
  console.log('Sending email');
}
```



This code will run when Pub/Sub posts a message to the service. This is what it does:

- It decodes the Pub/Sub message and then tries to call the `sendEmail()` function.
- If that succeeds and no exception is thrown, it will return status code 204 so Pub/Sub knows that the message was processed.
- If there is an exception, the service will return status code 500 so that Pub/Sub knows the message was not processed and it should re-post it to the service later.

Once the communication between services is working, Ruby will add code to the `sendEmail()` function to actually send the email.

6. Now create a file named `Dockerfile` and add the code below into it:

```
FROM node:18
WORKDIR /usr/src/app
COPY package.json package*.json ./
RUN npm install --only=production
COPY . .
CMD [ "npm", "start" ]
```



This file defines how to package up the Cloud Run service into a container.

### Deploy the Email Service

1. Create a new file called `deploy.sh` and add the following to it:

```
gcloud builds submit \
  --tag gcr.io/$GOOGLE_CLOUD_PROJECT/email-service

gcloud run deploy email-service \
  --image gcr.io/$GOOGLE_CLOUD_PROJECT/email-service \
  --platform managed \
  --region us-east1 \
  --no-allow-unauthenticated \
  --max-instances=1
```



2. Make `deploy.sh` executable:

```
chmod u+x deploy.sh
```



3. Deploy the Email Service:

```
./deploy.sh
```



When the deployment is complete, you will see a message similar to this:

```
Service [email-service] revision [email-service-00001] has been deployed and is serving traffic at https://email-service-[hash].a.run.app
```

The service has been successfully deployed. You now need to ensure the Email Service is triggered when a Pub/Sub message is available.

### Configure Pub/Sub to trigger the Email Service

Whenever a new Pub/Sub message is published using the "new-lab-report" topic, it should trigger the Email Service. To achieve this task, configure a service account to automatically handle the associated requests for this service.

![Architecture diagram highlights the flow from Cloud Pub/Sub to Email Service](https://cdn.qwiklabs.com/%2B8Zqu9LqE36YJc72Wu6ySfAuY9DiZ8pZE%2BnQPI80%2FFw%3D)

1. Create a new service account that will be used to trigger the services responding to Pub/Sub messages:

```
gcloud iam service-accounts create pubsub-cloud-run-invoker --display-name "PubSub Cloud Run Invoker"
```



2. Give the new service account permission to invoke the Email Service:

```
gcloud run services add-iam-policy-binding email-service --member=serviceAccount:pubsub-cloud-run-invoker@$GOOGLE_CLOUD_PROJECT.iam.gserviceaccount.com --role=roles/run.invoker --region us-east1 --platform managed
```



Next, tell Pub/Sub to invoke the SMS Service when a "new-lab-report" message is published.

3. Put the project number in an environment variable for easy access:

```
PROJECT_NUMBER=$(gcloud projects list --filter="qwiklabs-gcp" --format='value(PROJECT_NUMBER)')
```



Next, enable the project to create Pub/Sub authentication tokens.

4. Run the code below:

```
gcloud projects add-iam-policy-binding $GOOGLE_CLOUD_PROJECT --member=serviceAccount:service-$PROJECT_NUMBER@gcp-sa-pubsub.iam.gserviceaccount.com --role=roles/iam.serviceAccountTokenCreator
```



5. Put the URL of the Email Service in another environment variable:

```
EMAIL_SERVICE_URL=$(gcloud run services describe email-service --platform managed --region us-east1 --format="value(status.address.url)")
```



6. Confirm the EMAIL_SERVICE_URL has been captured:

```
echo $EMAIL_SERVICE_URL
```



7. Create a Pub/Sub subscription for the Email Service.

```
gcloud pubsub subscriptions create email-service-sub --topic new-lab-report --push-endpoint=$EMAIL_SERVICE_URL --push-auth-service-account=pubsub-cloud-run-invoker@$GOOGLE_CLOUD_PROJECT.iam.gserviceaccount.com
```



Nice work! The service is now set up to respond to Cloud Pub/Sub messages. As a next step, validate the code to confirm it meets requirements.

### Test the Lab Report Service and the Email Service together

1. Using the script created earlier, post to the lab reports again:

```
~/pet-theory/lab05/lab-service/post-reports.sh
```



2. Then open the log (**Navigation menu** > **Cloud Run**). You will see the two Cloud Run services, **email-service** and **lab-report-service**, in your account.

3. Click **email-service** and then click **Logs**.
   You will see the result of this service being triggered by Pub/Sub. If you don’t see the messages you expect, you may need to scroll up and down with the scrollbar to get the log to refresh.

Great job! The Email service is now able to write information to the log whenever a message is processed from the Cloud Pub/Sub topic queue! The last task is to write the SMS Service.

## Task 4. The SMS Service

Help Ruby to set up the new SMS Service.

![SMS Service highlighted in the architecture diagram](https://cdn.qwiklabs.com/Q2zCpYNvV%2FAyDZ6Cz35F4D9Rtdx2OycYXFD8E3O%2FCwI%3D)

### Add code for the SMS Service

1. Create a directory for the SMS Service:

```
cd ~/pet-theory/lab05/sms-service
```



2. Install the packages required to receive incoming HTTPS requests:

```
npm install express
npm install body-parser
```



3. Open the `package.json` file.

4. In the "scripts" section, add the `"start": "node index.js",` line as shown below and save the file:

```
...

"scripts": {
    "start": "node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },

...
```



**Note:** Be sure to add the code exactly as provided, including the ending comma:



```
"start": "node index.js",
```



Otherwise, you will encounter errors during deployment.

5. Create a new file called `index.js` and add the following to it:

```
const express = require('express');
const app = express();
const bodyParser = require('body-parser');
app.use(bodyParser.json());

const port = process.env.PORT || 8080;
app.listen(port, () => {
  console.log('Listening on port', port);
});

app.post('/', async (req, res) => {
  const labReport = decodeBase64Json(req.body.message.data);
  try {
    console.log(`SMS Service: Report ${labReport.id} trying...`);
    sendSms();

    console.log(`SMS Service: Report ${labReport.id} success :-)`);    
    res.status(204).send();
  }
  catch (ex) {
    console.log(`SMS Service: Report ${labReport.id} failure: ${ex}`);
    res.status(500).send();
  }
})

function decodeBase64Json(data) {
  return JSON.parse(Buffer.from(data, 'base64').toString());
}

function sendSms() {
  console.log('Sending SMS');
}
```



6. Now create a file named `Dockerfile` and add the code below into it:

```
FROM node:18
WORKDIR /usr/src/app
COPY package.json package*.json ./
RUN npm install --only=production
COPY . .
CMD [ "npm", "start" ]
```



This file defines how to package up the Cloud Run service into a container. Now the code has been created, the next step is to deploy the service.

### Deploy the SMS Service

1. Create a file named `deploy.sh` and add this code into it:

```
gcloud builds submit \
  --tag gcr.io/$GOOGLE_CLOUD_PROJECT/sms-service

gcloud run deploy sms-service \
  --image gcr.io/$GOOGLE_CLOUD_PROJECT/sms-service \
  --platform managed \
  --region us-east1 \
  --no-allow-unauthenticated \
  --max-instances=1
```



2. Make `deploy.sh` executable:

```
chmod u+x deploy.sh
```



3. Deploy the SMS Service:

```
./deploy.sh
```



When the deployment is complete, a message similar to this is displayed:

```
Service [sms-service] revision [sms-service-00001] has been deployed and is serving traffic at https://sms-service-[hash].a.run.app
```

The SMS Service is successfully deployed, but it isn't linked to the Cloud Pub/Sub service. Correct that in the next section.

### Configure Cloud Pub/Sub to trigger the SMS Service

As with the Email Service, the link between Cloud Pub/Sub and the SMS service needs to be configured so that messages can be consumed.

![The architecture diagram highlights the flow from Cloud Pub/Sub to SMS Service](https://cdn.qwiklabs.com/tARzXPlypfXhPCMY9kwYDNyKewY6nZ33xxEa2VOindg%3D)

1. Set the permissions to allow Pub/Sub to trigger the SMS Service:

```
gcloud run services add-iam-policy-binding sms-service --member=serviceAccount:pubsub-cloud-run-invoker@$GOOGLE_CLOUD_PROJECT.iam.gserviceaccount.com --role=roles/run.invoker --region us-east1 --platform managed
```



Next, tell Pub/Sub to invoke the SMS Service when a “new-lab-report” message is published.

2. The first step is to put the URL address of the SMS Service in an environment variable:

```
SMS_SERVICE_URL=$(gcloud run services describe sms-service --platform managed --region us-east1 --format="value(status.address.url)")
```



3. Confirm the SMS_SERVICE_URL has been captured:

```
echo $SMS_SERVICE_URL
```



4. Then create the Pub/Sub subscription:

```
gcloud pubsub subscriptions create sms-service-sub --topic new-lab-report --push-endpoint=$SMS_SERVICE_URL --push-auth-service-account=pubsub-cloud-run-invoker@$GOOGLE_CLOUD_PROJECT.iam.gserviceaccount.com
```



5. Run the test script again to post three lab reports to the Lab Report Service:

```
~/pet-theory/lab05/lab-service/post-reports.sh
```



6. Then open the log (**Navigation menu** > **Cloud Run**). You will see the three Cloud Run services, email-service, lab-report-service, and sms-service, in your account.

7. Click **sms-service**, then click **Logs**. You will see the result of this service being triggered by Pub/Sub.

The prototype system has been created and successfully tested. However, Patrick is concerned that resilience, as part of the initial validation process, hasn't been tested.

## Task 5. Test the resiliency of the system

What happens if one of the services goes down? Patrick has run into this before, as it is a common situation.

Help Ruby investigate how to ensure the system can handle this scenario. She wants to test what happens when a service fails by deploying a bad version of the Email Service.

1. Go back to the `email-service` directory:

```
cd ~/pet-theory/lab05/email-service
```



Add some invalid text to the Email Service application to cause an error.

2. Edit `index.js` and add the `throw` line to the `sendEmail()` function, as shown below. This will throw an exception, as if the email server was down:

```
...

function sendEmail() {
  throw 'Email server is down';
  console.log('Sending email');
}
...
```



The addition of this code will crash the service when it is invoked.

3. Deploy this bad version of the Email Service:

```
./deploy.sh
```



4. When the Email Service deployment has successfully completed, post data to the lab reports again, then go and watch the **email-service** log status closely:

```
~/pet-theory/lab05/lab-service/post-reports.sh
```



5. Open the Email Service logs to view the logs for the bad Email Service: **Navigation menu** > **Cloud Run**.

6. When you see the three Cloud Run services in your account, click **email-service**.

The Email Service is being invoked, but it will keep crashing. If you scroll back a bit in the logs you will find the root cause: “Email server is down”. You can also see that the service returns status code 500, and that Pub/Sub keeps retrying calling the service.

If you look at the logs from the SMS service, you will see that it operates successfully.

Now fix the error in the Email Service to restore the application!

7. Open the `index.js` file and remove the throw line you previously entered, then save the file.

Your `index.js` `sendEmail` function show now look similar to this:

```
function sendEmail() {
  console.log('Sending email');
}
```



8. Deploy the fixed version of the Email Service:

```
./deploy.sh
```



9. When the deployment has finished, click the **refresh** icon in the top right corner.

You will see how the emails for report 12, 34 and 56 were finally sent, the Email Service returned the status code 204, and Pub/Sub stopped invoking the service. No data was lost; Pub/Sub kept retrying until it was finally successful. This is the foundation of a robust system!

### Takeaways

1. If services communicate asynchronously with each other via Pub/Sub instead of calling each other directly, the system can be more resilient.
2. The Lab Report Service trigger is independent of other services, thanks to the use of Pub/Sub. For example, if customers should also want to receive lab results via another messaging service, it can be added without needing to update the Lab Report Service.
3. Cloud Pub/Sub handled the retries, the services didn't have to. Services are only required to return a status code: success or failure.
4. If a service goes down, the system is capable of automatically "healing" itself when the service comes back online, thanks to Pub/Sub retries.

## Congratulations!

Ruby, with your help, has successfully built a resilient prototype system. The service is capable of automatically sending every client an email and SMS message. In the event of individual services being temporarily down, the system will implement a retry mechanism so that no data is lost. Ruby receives some well deserved accolades...

| ![Lily](https://cdn.qwiklabs.com/SAe6MsJi2voh0ygak%2BAV2SzyXCCtjirn9cKOaQV2nU4%3D)*Lily, Founder of Pet Theory* | Hey Ruby,I can't express our gratitude for all your hard work and leadership.Over a very short period of time our essential systems have been totally revamped.We are having a small gathering on Friday to celebrate and it would be great if you would be our guest of honor!Lily |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Melody](https://cdn.qwiklabs.com/1bqOwZ3NVxZM4l8Ys9ZG%2FNoae3eNGdyVj9bHuBYMF%2Bo%3D)*Melody, Managing Director* | Ruby,I have received high praise for your work from Pet Theory. You are a tremendous credit to the team.Now that you're finished with this assignment, I would like to talk to you about a more senior role on a new project.MelodyManaging DirectorComputer Consulting Inc. |

### Next steps / Learn more

- Medium article: [Cloud Run as an internal async worker](https://medium.com/google-cloud/cloud-run-as-an-internal-async-worker-480a772686e)
