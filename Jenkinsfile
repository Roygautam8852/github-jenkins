pipeline {

    agent any

    parameters {

        string(
            name: 'BRANCH_NAME',
            defaultValue: 'main',
            description: 'Git Branch Name'
        )

        string(
            name: 'APP_VERSION',
            defaultValue: '1.0',
            description: 'Application Version'
        )
    }

    environment {

        BUILD_DIR = 'target'

        ARTIFACT_NAME = "app-${APP_VERSION}.jar"
    }

    stages {

        stage('Checkout') {

            steps {

                echo "Checking out branch ${BRANCH_NAME}"

                git branch: "${BRANCH_NAME}",
                url: 'https://github.com/Roygautam8852/github-jenkins.git'
            }
        }

        stage('Build') {

            steps {

                echo "Building Application"

                sh 'mvn clean compile'
            }
        }

        stage('Unit Testing') {

            steps {

                echo "Running Tests"

                sh 'mvn test'
            }
        }

        stage('Code Quality Check') {

            steps {

                echo "Performing Code Quality Check"

                sh 'mvn verify'
            }
        }

        stage('Packaging') {

            steps {

                echo "Creating Artifact"

                sh 'mvn package'
            }
        }
    }

    post {

        success {

            echo 'Pipeline Executed Successfully'
        }

        failure {

            echo 'Pipeline Failed'
        }
    }
}