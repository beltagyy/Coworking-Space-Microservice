# Enhanced Coworking Space Service Extension

The Coworking Space Service is a robust suite of APIs designed to streamline the management and operational efficiency of coworking spaces. It empowers users by providing them with the ability to request one-time access tokens and grants administrators the capability to authorize entry to the premises. This service is architected on a microservices paradigm, ensuring that each API component operates independently for scalable deployment and easier maintenance.

As a DevOps engineer, you will engage in a collaborative endeavor with a development team dedicated to creating an API tailored for business analysts. This API is instrumental in delivering essential analytics on user interactions within the coworking space service. The local version of the application is fully functional, and your expertise is crucial in establishing a continuous deployment pipeline for Kubernetes integration.

## Initial Configuration

To begin the setup process, please follow these steps:

1. **Repository Cloning**:
   - Execute a `git clone` command to retrieve the repository contents.

2. **Database Initialization**:
   - Build the provided database Dockerfile located in the 'db' directory. You'll need to supply arguments to establish the database connections properly.

3. **Application Configuration**:
   - Construct the application's Dockerfile, incorporating runtime variables to configure `DB_USERNAME` and `DB_PASSWORD`. Ensure these credentials are consistent with the ones specified in step 2.

## Contribution Guidelines for Analytics Enhancement

To contribute to the analytics service, adhere to the following workflow:

1. **Branch Creation**:
   - Generate a new branch off the development branch for your feature or fix.

2. **Code Integration**:
   - Implement your changes within `app.py`. Subsequently, commit your updates and push them to your branch.

3. **Pull Request and Review**:
   - Initiate a pull request targeting the development branch. Your contributions will undergo a thorough review process.

4. **Testing and Merging**:
   - Following a successful code review and passing all necessary tests, your code will be merged into the development branch. It will ultimately make its way into the main branch, leading to deployment.

## Deployment Pipeline

The merge into the main branch triggers an automated deployment sequence:

1. **AWS CodeBuild Pipeline Activation**:
   - The `buildspec.yml` file execution begins within AWS CodeBuild, processing and packaging the application.

2. **Docker Image Repository**:
   - AWS CodeBuild pushes the newly built Docker image to an Amazon ECR repository.

3. **Kubernetes Deployment**:
   - Utilizing the Image ARN, the `analytics-api.yml` deployment file is updated. This file, alongside the database configuration files, orchestrates the service deployment on Kubernetes.

4. **Service Availability**:
   - The associated pods within the analytics service are initiated, bringing the application online and operational.

## Additional Resources

For more detailed instructions, best practices, and guidelines, please refer to the project's wiki and documentation pages on the repository. Your contributions are invaluable, and we look forward to your innovative solutions to enhance our Coworking Space Service.
