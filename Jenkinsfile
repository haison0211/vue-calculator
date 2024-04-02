pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            // args '-u root'
        }
    }
    
    stages {
        stage('Hello') {
            steps {
                echo 'Hello, world! develop'
                npm install
            }
        }
    }
}
