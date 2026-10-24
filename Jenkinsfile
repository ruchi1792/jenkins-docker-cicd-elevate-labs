pipeline {
    agent any

    environment {
        IMAGE_NAME = 'jenkins-demo:latest'
        CONTAINER_NAME = 'jenkins-demo-app'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t "$IMAGE_NAME" .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application files and Docker image...'
                sh 'test -f index.html'
                sh 'grep -q "Jenkins CI/CD Pipeline Successful!" index.html'
                sh 'docker image inspect "$IMAGE_NAME" >/dev/null'
                echo 'All basic tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application container...'
                sh '''
                    docker rm -f "$CONTAINER_NAME" || true
                    docker run -d \
                        --name "$CONTAINER_NAME" \
                        --restart unless-stopped \
                        -p 8081:80 \
                        "$IMAGE_NAME"
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check Console Output for details.'
        }
    }
}
