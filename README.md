# Continuous Integration and Continuous Deployment (CI/CD) Pipeline for Application Deployment

This repository hosts a comprehensive Jenkins pipeline script designed to orchestrate the CI/CD process for deploying applications. The pipeline automates key stages of the software delivery lifecycle, including compilation, testing, static code analysis, Docker image building, vulnerability scanning, deployment to Kubernetes, and post-deployment verification.

## Pipeline Overview

The CI/CD pipeline is meticulously structured to ensure seamless software delivery:

1. **Git Checkout**: Initiates the retrieval of source code from the repository for subsequent processing.
2. **Compile**: Utilizes Maven to compile the application source code into executable artifacts.
3. **Test**: Executes unit tests to validate the functionality and integrity of the application.
4. **File System Scan**: Conducts a comprehensive vulnerability analysis of the file system using Trivy.
5. **SonarQube Analysis**: Performs rigorous static code analysis via SonarQube to enhance code quality.
6. **Quality Gate**: Verifies adherence to quality gate criteria, ensuring the code meets predefined standards.
7. **Build**: Packages the application into distributable units ready for deployment.
8. **Publish To Nexus**: Deploys the built artifacts to Nexus repository manager for efficient artifact management.
9. **Build & Tag Docker Image**: Constructs and tags a Docker image to facilitate containerized deployment.
10. **Docker Image Scan**: Conducts thorough vulnerability scanning of the Docker image using Trivy.
11. **Push Docker Image**: Pushes the Docker image to a designated Docker registry for availability.
12. **Deploy To Kubernetes**: Orchestrates the deployment of the application to a Kubernetes cluster.
13. **Verify the Deployment**: Validates the successful deployment by retrieving pertinent information about pods and services.

## Requirements

To effectively utilize this CI/CD pipeline, ensure the following prerequisites are met:

- Jenkins instance configured with requisite plugins.
- SonarQube server configured for comprehensive static code analysis.
- Trivy installed for robust vulnerability scanning.
- Docker installed to facilitate Docker image building and registry operations.
- Kubernetes cluster properly configured to support application deployment.

## Usage

1. **Jenkins Setup**: Create a Jenkins job and configure it to use this pipeline script.
2. **Credentials**: Set up Jenkins credentials for Git, SonarQube, Docker registry, and Kubernetes.
3. **Configure Tools**: Ensure that JDK, Maven, SonarQube scanner, and Docker are configured in Jenkins Global Tool Configuration.
4. **Environment Variables**: Adjust the environment variables as per your setup, especially `SCANNER_HOME`.
5. **Pipeline Execution**: Trigger the Jenkins job manually or configure it to be triggered automatically upon code changes.
6. **Monitor**: Monitor the pipeline execution in Jenkins and review the console output for any errors or warnings.
7. **Notifications**: Configure email notifications as per your requirement.

## Author

This CI/CD pipeline script was authored by Yash Raj Mathur. 

For any issues or feedback, please contact yashrajmathur71@gmail.com.
