
# Up-Cancer-Workspace

This repository contains a showcase of my projects, with a focus on both **front-end** and **back-end** development. The main project in this workspace is a serverless backend for a contact management system, demonstrating skills in cloud infrastructure, serverless architecture, and modern JavaScript development.

## Project Overview

### Contact System Backend
This project implements a backend API for managing contacts, built using Node.js and the Serverless Framework, and deployed on AWS Lambda. It uses DynamoDB for data storage and provides a RESTful endpoint to create new contacts. The backend is designed for scalability, cost-efficiency, and ease of deployment.

#### How It Works
- The backend exposes a POST endpoint `/contact` for creating new contact records.
- Incoming requests are validated for required fields (first name, last name, email, phone number, contact owner).
- A counter in DynamoDB is atomically incremented to generate a unique contact ID.
- The contact data is stored in a DynamoDB table with the generated ID and a timestamp.
- The API is deployed and managed using the Serverless Framework, allowing local development and easy cloud deployment.

## Technologies Used

- **Back-end**: Node.js, AWS Lambda, Serverless Framework
- **Infrastructure as Code**: serverless.yml (Serverless Framework)
- **Database**: AWS DynamoDB
- **Local Development**: serverless-offline
- **Version Control**: Git, GitHub

## Project Structure

- `contactbackend/` - Main backend project
   - `package.json` - Project dependencies and scripts
   - `serverless/infrastructure/serverless.yml` - Serverless deployment configuration
   - `serverless/src/functions/auth/contacts/contact.js` - Lambda function for contact creation
   - `serverless/src/functions/auth/register/ContactEvent.json` - Sample event for local testing
   - `Serverless_Command.txt` - Usage instructions for local invocation

## How to Run the Project Locally

1. **Install dependencies**
    - Navigate to the `contactbackend` directory and run:
       ```
       npm install
       ```

2. **Start local development server**
    - From the `contactbackend/serverless/infrastructure` directory (where `serverless.yml` is located), run:
       ```
       npx serverless offline
       ```

3. **Invoke the function locally**
    - You can test the function using:
       ```
       serverless invoke local --function contact --path ../src/functions/auth/register/ContactEvent.json
       ```

4. **Deploy to AWS**
    - To deploy the backend to AWS Lambda, run:
       ```
       serverless deploy
       ```

## Additional Notes

- The backend is designed to be stateless and scalable, leveraging AWS Lambda and DynamoDB.
- All configuration for AWS resources is managed in `serverless.yml`.
- For more details on the backend logic, see `contact.js` in the source directory.

---

A portfolio repository to demonstrate the skills and technologies I've utilized across various web development projects.


