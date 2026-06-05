pipeline {

    agent any

    parameters {

        string(name: 'BRANCH_NAME', defaultValue: 'main')
        string(name: 'APP_VERSION', defaultValue: '1.0')
    }

    environment {

        BUILD_DIR = 'target'

        ARTIFACT_NAME = "app-${APP_VERSION}.jar"
    }

    stages {

        stage('Checkout') {
            steps {
                echo "Checking out ${BRANCH_NAME}"
            }
        }

        stage('Build') {
            steps {
                echo "Build Successful"
            }
        }

        stage('Unit Testing') {
            steps {
                echo "Unit Tests Passed"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Code Quality Check Passed"
            }
        }

        stage('Packaging') {
            steps {
                echo "Artifact ${ARTIFACT_NAME} Created"
            }
        }
    }

    post {
        success {
            echo "Pipeline Executed Successfully"
        }
    }
}