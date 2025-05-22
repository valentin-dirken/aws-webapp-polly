# School19 Text-to-Speech Serverless Application Workshop

## Overview

Welcome to the School19 Text-to-Speech Serverless Application Workshop! In this hands-on workshop, you'll build a completely serverless application that converts text into natural-sounding speech using Amazon Polly, with a modern web interface for interacting with your application.

![Architecture Diagram](https://static.us-east-1.prod.workshops.aws/public/2b2654d0-25fc-498c-9d95-069507fc0346/static/images/architecture.png)

## What You Will Learn

By completing this workshop, you will learn how to:

- Create a serverless architecture using multiple AWS services working together
- Build an Amazon DynamoDB table to store application data
- Create a RESTful API with Amazon API Gateway
- Implement application logic using AWS Lambda functions
- Connect components using Amazon SNS for asynchronous processing
- Convert text to speech with Amazon Polly
- Deploy a static website on Amazon S3
- Secure your application with appropriate IAM roles and policies

## Prerequisites

- An AWS account with administrator access
- Basic familiarity with AWS services
- Basic understanding of JavaScript, HTML, and Python
- A modern web browser

## Workshop Duration

This workshop requires approximately 90 minutes to complete.

## Architecture Overview

The application you'll build consists of two main workflows:

### 1. Creating a New Post (Text-to-Speech Conversion)

1. A user enters text on the web interface hosted on Amazon S3
2. The request is sent to Amazon API Gateway, which triggers the NewPost Lambda function
3. The Lambda function stores the post data in DynamoDB and sends a message to an SNS topic
4. The ConvertToAudio Lambda function is triggered by the SNS message
5. This function uses Amazon Polly to convert the text to an MP3 audio file
6. The audio file is stored in an S3 bucket
7. The DynamoDB record is updated with the URL to the audio file

### 2. Retrieving Posts

1. A user searches for posts on the web interface
2. The request is sent to Amazon API Gateway, which triggers the GetPost Lambda function
3. The function retrieves the requested post data from DynamoDB and returns it to the user
4. The user can play the audio file directly from the web interface

## Workshop Modules

1. **Create Resources** - Set up DynamoDB, S3, and SNS
2. **Create Lambda Functions** - Implement the application logic
3. **Configure API Gateway** - Create a RESTful API
4. **Deploy Web Interface** - Host a static website on S3
5. **Test the Application** - Verify everything works end-to-end

## Files Included

- `index.html` - Main web interface
- `scripts.js` - JavaScript for the web interface
- `styles.css` - CSS for styling the web interface
- Lambda function code for:
  - PostReader_NewPost
  - ConvertToAudio
  - PostReader_GetPost

## Security Considerations

This workshop focuses on functionality, but in a production environment, you would want to implement:

- HTTPS for all communications
- More restrictive IAM policies
- Authentication and authorization
- Input validation
- Rate limiting

## Cleanup

After completing the workshop, remember to delete all resources to avoid incurring additional charges:

1. Empty and delete the S3 buckets
2. Delete the DynamoDB table
3. Delete the Lambda functions
4. Delete the API Gateway API
5. Delete the SNS topic

## Next Steps

After completing this workshop, consider these enhancements:

- Add user authentication
- Add support for more languages
- Implement a voice selection feature
- Add a caching layer for frequently accessed posts
- Deploy through CI/CD pipelines

## Support

If you have questions or need assistance during the workshop, please reach out to Valentin.

Happy building!

---

© Valentin Dirken - AWS, 2025
