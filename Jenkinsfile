pipeline {
    triggers {
        pollSCM '*/5 * * * *'
    }
    agent {
        node {
            label 'dev'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Jenkins
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo "Deliver..."
                sh '''
                echo "doing delivery stuff..."
                '''
            }
        }
    }
}
