# Dream-Vaccation-App
# Dream Vacation Destinations

This application allows users to create a list of countries they'd like to visit, providing basic information about each country. The project is structured to mimic a real-life production environment, employing best practices in software development, deployment, and continuous integration/continuous delivery (CI/CD).

## Setup

### Backend
1. Navigate to the `backend` directory.
2. Run `npm install` to install dependencies.
3. Set up your MySQL database and update the `.env` file with your database URL.
4. Run `npm start` to start the server.

### Frontend
1. Navigate to the `frontend` directory.
2. Run `npm install` to install dependencies.
3. Update the `.env` file with your API URL (e.g., `REACT_APP_API_URL=http://localhost:3001`).
4. Run `npm start` to start the React development server.

## Features
- **Add Countries**: Users can add countries to their dream vacation list.
- **View Country Details**: Displays capital, population, and region information for each country.
- **Remove Countries**: Users can remove countries from their list.
- **Production-Ready Setup**: The project is designed to be scalable and maintainable, following industry-standard practices for deployment and CI/CD.

## Containerization
1. Write Dockerfiles for the Frontend and Backend based on the backend technology
2. Create a .dockerignore file for backend and add these files: node_modules, npm-debug.log, .env       Contributing.md, README.md
3. Create a .dockerignore file for frontend and add these files: node_modules, npm-debug.log, .env, Contributing.md, README.md
4. Write your docker-compose.yml file.
5. Run the docker compose command to build and run everything `docker-compose up --build -d`
6. Containers are running locally and you can view the frontend at  http://localhost:3000

## Deployment to the Cloud
- We are using 
` **Amazon EC2** (for hosting the app)
- **Amazon RDS** (for managed MySQL database)
- **DockerHub** for container distribution
- Tag and push images to dockerhub
- Provision an EC2 instance and add inbound rules to the security group for ports 22 (SSH), 3000 (frontend), and 3001 (backend)
- SSH into the server and install docker and dependencies. Also install MySQL client
- Set up RDS in the cloud and ensure open port 3306. Note the endpoint. Create a db called dreamvacation
- Dump local db and upload it to EC2
- Send db from EC2 to RDS`mysql -h <rds-endpoint> -u admin -p --database=dreamvacation < dreamvacation.sql`
- Deploy application on EC2 with docker compose `docker-compose up --build`
## Technologies Used
- **Frontend**: React
- **Backend**: Node.js with Express
- **Database**: MySQL
- **External API**: REST Countries API
- **CI/CD**: To be implemented with [CI/CD tools, e.g., GitHub Actions, Jenkins, or Azure DevOps]
- **Infrastructure as Code**: To be implemented with tools like Terraform or Helm

## Best Practices
- **Version Control**: All changes are tracked in Git for collaboration and history management.
- **Environment Management**: Separate configurations for different environments (development, staging, production) using environment variables.
- **Security**: Sensitive information is managed using environment variables and Kubernetes Secrets.
- **Documentation**: The project is well-documented to facilitate onboarding and maintenance.
