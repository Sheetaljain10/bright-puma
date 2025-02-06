pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building application..."
                    sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Running tests..."
                    sh 'pytest'  // If using PyTest for unit testing
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying application..."
                    sh 'python app.py &'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    echo "Application is running on port 5000"
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline execution completed"
        }
    }
}
