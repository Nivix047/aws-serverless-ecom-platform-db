# Severless Application using AWS - RDS Database Management

## Project Overview

This repository is part of a larger project and focuses exclusively on the **database** management using **AWS RDS (PostgreSQL)**. The database is containerized using **Docker**, and the project is designed to ensure secure, scalable, and efficient database management in the cloud. Key features include **data encryption at rest**, automated **backup and recovery** strategies, and integration with a broader AWS architecture.

The other components of the project—such as **Lambda functions**, **API Gateway**, and **ECR**—will be managed in a separate repository. For more details on these components, you can find the Lambda functions repository here:

- **[AWS Lambda Functions Repository](https://github.com/Nivix047/aws-serverless-ecom-platform-functions)**

The overall goal is to test **AWS deployment** and build a **serverless cloud structure**.

## Key Features

- **AWS RDS (PostgreSQL)**: Used for managing relational data with high availability, automated backups, and encryption at rest.
- **Docker Containerization**: Ensures consistent environment setup for database management and testing.
- **Data Encryption at Rest**: All data stored in AWS RDS is encrypted using AWS KMS to ensure security.
- **Backup and Recovery**: Automated backup configuration and point-in-time recovery to prevent data loss.

## Repository Contents

This repository contains the following key files:

1. **init-db/init.sql**: SQL script to initialize the database with tables (`users`, `products`, `purchases`) and sample data.
2. **app.py**: Python script to establish a connection to the RDS instance and run the SQL script for database initialization.
3. **Dockerfile**: Defines the containerized environment using Python 3.11, and installs necessary dependencies.
4. **docker-compose.yml**: Sets up the containerized services for the project, including environment variables for database connection.
5. **.env**: A file (not included in this repo for security reasons) that contains environment variables like database host, port, username, and password.

## Getting Started

### Prerequisites

- AWS RDS instance for PostgreSQL, set up with **data encryption at rest** and **automated backups**.
- Docker and Docker Compose installed on your local machine.
- API testing tools like **Postman** or **Insomnia** for testing the CRUD operations.

### Setup Steps

1. **Create AWS RDS Instance**:

   - Set up a PostgreSQL RDS instance via the AWS Management Console.
   - Ensure the instance is in a private VPC and has encryption at rest enabled.
   - Configure automated backups and point-in-time recovery.

2. **Configure Environment Variables**:

   - Create a `.env` file at the root of your project directory with the necessary environment variables.

3. **Run the Application**:

   - Build and run the Docker containers using Docker Compose:

     ```bash
     docker-compose up --build
     ```

   - This will set up a Python container that connects to the RDS instance and initializes the database with the SQL scripts.

4. **Verify Database Setup**:
   - Use a PostgreSQL client or API testing tools like **Postman** or **Insomnia** to verify that the `users`, `products`, and `purchases` tables have been created in your RDS instance.
   - Sample data should also be present in these tables, as defined in `init.sql`.

## Security and Best Practices

- **Encryption at Rest**: AWS KMS is used to ensure that all data stored in RDS is encrypted.
- **IAM Roles**: Use least-privilege IAM roles to restrict access to the RDS instance.
- **Backup and Recovery**: Automated backups and point-in-time recovery are enabled to safeguard against data loss.

## Technologies Used

- **AWS RDS (PostgreSQL)**: Relational database management.
- **Docker**: Containerization for local development.
- **psycopg2**: PostgreSQL adapter for Python to interact with the database.

## Contributing

Feel free to submit issues or pull requests if you find bugs or have suggestions to improve the project.

## Feedback

Always open to feedback and looking forward to connecting with professionals in the tech space!
