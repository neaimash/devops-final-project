pipline {
    agent any

    environment {
        DOCKER_IMAGE = "neaimash/flask-app"
        IMAGE_TAG = "v1"
        HELM_RELEASE = "flask"
        HELM_CHART_PATH = "helm/flask"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t %DOCKER_IMAGE%:%IMAGE_TAG% .'
            }
        }
        stage('test') {
            steps {
                bat 'docker run -d --name flask-test -p 5000:5000 %DOCKER_IMAGE%:%IMAGE_TAG%'
                bat 'timeout /t 10'
                echo 'Testing endpoint with curl...'
                bat 'curl --fail http://localhost:5000'
                bat 'docker stop flask-test'
                bat 'docker rm flask-test'
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploying Flask app with Helm...'
                bat 'helm upgrade --install %HELM_RELEASE% %HELM_CHART_PATH%'
                }
            }
        }
    }
}
