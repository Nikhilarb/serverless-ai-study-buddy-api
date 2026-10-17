# Serverless AI Study Buddy API

An AI-powered study assistant built using AWS serverless services, Python, and Anthropic Claude. The API generates study guides, quizzes, and topic summaries, while storing study-request history in Amazon DynamoDB.

## Project Overview

This project explores integrating a third-party AI model into a serverless AWS application. It combines REST API endpoints, Python-based AWS Lambda functions, reusable dependency packaging, credential handling, and persistent request history.

**Project status:** Completed and tested. AWS resources were removed after testing as part of cost and security cleanup. The API is not currently deployed.

## Architecture

The application uses the following services:

- **Amazon API Gateway:** Exposes the API endpoints.
- **AWS Lambda:** Runs the Python application logic.
- **Amazon DynamoDB:** Stores and retrieves study-request history.
- **AWS Lambda Layer:** Packages reusable Python SDK dependencies.
- **AWS IAM:** Controls access to AWS resources.
- **Anthropic Claude API:** Generates AI-powered study content.

### API Endpoints

- `POST /study` — Generates study materials based on a submitted topic.
- `GET /history` — Retrieves previously stored study-request history.

## Key Features

- Generates study guides, quizzes, and topic summaries.
- Integrates AWS Lambda with the Anthropic Claude API.
- Stores study-request history in DynamoDB.
- Packages the Anthropic Python SDK in a reusable Lambda Layer.
- Uses a Lambda environment variable for the external API key instead of hardcoding it in the source code.
- Applies IAM permissions to AWS resources.
- Includes troubleshooting of dependency, routing, and API integration issues.

## Technical Challenges and Troubleshooting

### Python Dependency Packaging

Packaged the Anthropic Python SDK into a reusable Lambda Layer using AWS CloudShell.

### API Gateway Routing

Troubleshot a `Missing Authentication Token` response caused by an incorrect request URL containing a duplicated `/study` path.

### Credential and Resource Management

Kept the external API key outside the application source code and removed deployed AWS resources after testing.

## Security Considerations

- Never commit API keys or AWS credentials.
- Use appropriate IAM permissions for each Lambda function.
- Keep external API credentials out of source code.
- Review logs and example payloads before sharing them publicly.

## Limitations

- The API is not currently deployed.
- The original endpoints are no longer available because the AWS resources were removed.
- Generated content, latency, and API costs depend on the external AI provider and model.

## Skills Demonstrated

AWS Lambda · Amazon API Gateway · Amazon DynamoDB · Python · REST APIs · AWS IAM · Lambda Layers · Third-party API integration · Generative AI · Troubleshooting · Cloud security · Serverless architecture

## Learning Outcomes

This project extended my hands-on experience with serverless AWS development into AI-powered API integration. It provided practical experience with Python dependencies, API endpoint design, database-backed request history, credential handling, and troubleshooting integration issues.
