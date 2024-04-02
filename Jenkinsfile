pipeline {
    agent {
        docker {
            image 'node:latest'
            args '-u root'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Install dependencies!'
                sh 'npm install'
            }
        }
    }
}
