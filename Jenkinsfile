pipeline {
    agent {
        docker {
            image 'node:latest'
            // args '-u root'
        }
    }
    
    stages {
        stage('Hello') {
            steps {
                echo 'Hello, world! develop'
                sh npm install
            }
        }
    }
}
