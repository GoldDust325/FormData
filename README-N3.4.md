## Lab N3.4 — Deploying SmartSpeechCoach to AWS Elastic Beanstalk

### Objective

Deploy the SmartSpeechCoach Node.js/Express backend from Lab N3.3 to AWS Elastic Beanstalk, test the AI functionality, and compare AWS Elastic Beanstalk with Google Cloud Run.

### AWS Deployment Steps

1. Downloaded the group's SmartSpeechCoach project from GitHub.
2. Opened the project in WebStorm and installed the Node.js dependencies.
3. Verified that the backend runs locally using `npm start`.
4. Created a ZIP containing `server.js`, `package.json`, and `package-lock.json`.
5. Opened AWS Academy Learner Lab and launched the AWS Management Console.
6. Created an AWS Elastic Beanstalk application named `CS651-Lab-N3-4`.
7. Selected Node.js 24 on Amazon Linux 2023.
8. Configured the environment using `LabRole` and `LabInstanceProfile`.
9. Selected a single `t3.micro` EC2 instance.
10. Uploaded the backend ZIP and configured the required environment variables.
11. Deployed the application and verified `/api/health`.
12. Tested the Gemini API endpoint and verified communication between the React frontend and AWS backend.

### Backend Changes

Updated `server.js` to use the Gemini `generateContent()` method instead of the Interactions API.

Selected the `gemini-3.5-flash` model after testing API compatibility and availability.

### AWS Deployment

**Platform:** AWS Elastic Beanstalk  
**Environment:** CS651-Lab-N3-4-env-1  
**Runtime:** Node.js 24  
**Instance:** t3.micro  
**Region:** us-east-1

**Backend URL:**

http://cs651-lab-n3-4-env-1.eba-3fguzp98.us-east-1.elasticbeanstalk.com

**Health endpoint:** `/api/health`  
**AI endpoint:** `POST /api/askanything`

The deployment URL is available while the AWS Academy environment is running.

### AWS vs. Google Cloud Run

| Feature | AWS Elastic Beanstalk | Google Cloud Run |
|---|---|---|
| Deployment | Node.js source ZIP | Source or container |
| Infrastructure | Managed EC2 resources | Serverless containers |
| Scaling | EC2-based scaling | Automatic scaling, including scale-to-zero |
| Configuration | IAM roles and environment properties | Cloud Run service configuration |
| Cost | Underlying AWS resources | Usage-based billing |
| Management | More infrastructure configuration | Less infrastructure management |

### Testing

- Local backend health check: Passed
- AWS backend health check: Passed
- Local Gemini API request: Passed
- AWS Gemini API request: Passed
- React frontend calling AWS backend: Passed
- Browser Network inspection: HTTP 200 OK

### Individual Contribution

Lab N3.4 deployment was completed using AWS Elastic Beanstalk by Matthew Chou. Work included configuring IAM roles, provisioning the environment, deploying the backend, debugging Gemini API requests, updating the Node.js backend, verifying frontend/backend communication, and documenting the deployment process.

### Conclusion

Lab N3.4 demonstrated that the same SmartSpeechCoach backend can run on AWS Elastic Beanstalk in addition to Google Cloud Run. This lab provided practical experience with cloud deployment, IAM configuration, troubleshooting API requests, and integrating a React frontend with a deployed Node.js backend.