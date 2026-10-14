# NodeJS + Express (w/EJS) Code to exercise reading in form data and returning a response

This code has a / path (mapped to index.js --> index.ejs) which displays 3 forms each mapped to a different 
uri path in index.js that executes different controller code (for simplicity --as this is simple code, left controller
code in index.js rather than in the controllers directory --which is a better MVC code styling format).   Here is the interface

![image](https://github.com/grewe/FormData/assets/11790686/58f45881-96d6-4275-82a1-f8b291d1475c)


After hitting the Go button on the first form this is what the results will look like (notice it has read in the form data)
![image](https://github.com/grewe/FormData/assets/11790686/06ab7aed-cdaf-4e18-867b-2bf82061a372)

## Lab N3.1: Node.js and Express Deployment to Google Cloud Run

### Project Overview

This lab demonstrates how to run a Node.js and Express web application locally and deploy it to Google Cloud Run using 
a GitHub repository and Google Cloud Build.

The application contains HTML forms that demonstrate GET and POST requests. Express processes the submitted form data 
and returns an HTML response.

### GitHub Repository

https://github.com/GoldDust325/FormData

### Local Development

1. Open the FormData project in WebStorm.
2. Open the terminal in the project directory.
3. Install dependencies using `npm install`.
4. Start the application using `npm start`.
5. Open `http://localhost:3000` in a browser.
6. Test the New Customer Form by entering a name and email address.
7. Stop the local server using `Ctrl + C` in the terminal.

### Google Cloud Run Deployment

**Google Cloud Project:** cs651-labn3

**Cloud Run Service:** formdata-n3-1

**Region:** us-west1 (Oregon)

**Deployment Method:** GitHub repository with Google Cloud Build

**Branch:** master

**Build Type:** Google Cloud Buildpacks for Node.js

**Application URL:**

https://formdata-n3-1-496118978198.us-west1.run.app

### Deployment Steps

1. Open Google Cloud Console and select the cs651-labn3 project.
2. Navigate to Cloud Run and select Create Service.
3. Choose continuous deployment from a repository.
4. Connect GitHub using Google Cloud Build.
5. Select the GoldDust325/FormData repository.
6. Configure the master branch using `^master$`.
7. Select Google Cloud Buildpacks.
8. Set the build context directory to `/`.
9. Name the service `formdata-n3-1` and select `us-west1`.
10. Allow public access for the classroom demonstration.
11. Select request-based billing and automatic scaling.
12. Set the minimum number of instances to 0 and maximum to 1.
13. Create the service and wait for the deployment to complete.
14. Open the Cloud Run URL and test the application.

### Testing and Verification

**Local testing:** Successfully started the Express application on port 3000 and submitted customer information through 
the HTML form.

**Cloud testing:** Successfully deployed the application and submitted customer information through the public 
Cloud Run URL.

Both environments returned the submitted name and email address correctly.

### Stopping the Application

**Local:** Press `Ctrl + C` in the WebStorm terminal to stop the Node.js server.

**Google Cloud Run:** With the minimum instance count set to 0, Cloud Run can automatically scale down when there 
are no requests. This does not disable the public endpoint. To prevent further requests, restrict access or disable 
the service's traffic through an appropriate administrative procedure.

### Individual Contribution

GoldDust325 configured the local development environment, verified the Express application's functionality, connected 
the GitHub repository to Google Cloud Build, deployed the application to Google Cloud Run, and tested the deployed 
application.