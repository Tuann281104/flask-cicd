pipeline {
    agent any
    environment {
        IMAGE = 'flask-cicd-local'
    }
    stages {
        stage('Clone') {
            steps {
                echo 'Code đang nằm trong workspace local'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flaskdemo $IMAGE || true'
            }
        }
    }
}
