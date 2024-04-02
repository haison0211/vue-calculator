pipeline {
    agent {
        docker {
            image 'node:latest'
            // args '-u root'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Install dependencies! develop'
                    sh npm install   
                }
            }
        }
    }
}
