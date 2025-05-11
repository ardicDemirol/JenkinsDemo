# JenkinsDemo

**JenkinsDemo** is a demo project that showcases the integration of Jenkins with a .NET-based application. This repository demonstrates Continuous Integration (CI) and Continuous Deployment (CD) pipelines, providing a practical example of automating workflows.

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Jenkins Pipeline](#jenkins-pipeline)
- [Contributing](#contributing)
- [License](#license)

## Features
- **CI/CD Integration**: Automates the build, test, and deployment processes.
- **Docker Support**: Containerized application for consistent environments.
- **.NET Core Application**: Demonstrates a simple .NET Core example integrated with Jenkins.

## Technologies Used
The project leverages the following technologies:
- **C# (.NET Core)**: The primary language for the application.
- **Docker & Dockerfile**: Ensures environment consistency and supports containerization.
- **Jenkins**: Automates the build and deployment pipelines.

## Getting Started

### Prerequisites
- **.NET Core SDK**: Install from [here](https://dotnet.microsoft.com/).
- **Docker**: Install from [here](https://www.docker.com/).
- **Jenkins**: Set up Jenkins on your system. See [Jenkins Installation Guide](https://www.jenkins.io/doc/book/installing/).

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ardicDemirol/JenkinsDemo.git
   ```
2. Navigate to the project directory:
   ```bash
   cd JenkinsDemo
   ```
3. Build the application:
   ```bash
   dotnet build
   ```

### Running the Application Locally
1. Run the application:
   ```bash
   dotnet run
   ```
2. Access the application in your browser at `http://localhost:5000`.

### Using Docker
1. Build the Docker image:
   ```bash
   docker build -t jenkins-demo .
   ```
2. Run the Docker container:
   ```bash
   docker run -p 5000:5000 jenkins-demo
   ```

## Jenkins Pipeline
This demo includes a sample Jenkins pipeline for automating CI/CD workflows. Below is an example of a Jenkinsfile used for this project:

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'dotnet build'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'dotnet test'
                }
            }
        }
        stage('Docker Build') {
            steps {
                script {
                    sh 'docker build -t jenkins-demo .'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment steps here
            }
        }
    }
}
```

### Configuring Jenkins
1. Add this repository to your Jenkins job.
2. Use the provided `Jenkinsfile` for the pipeline configuration.
3. Ensure that Docker and .NET Core are installed on your Jenkins agent.

## Contributing
Contributions are welcome! If you'd like to contribute, please follow these steps:

1. Fork this repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/YourFeatureName
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add your meaningful commit message"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/YourFeatureName
   ```
5. Submit a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
