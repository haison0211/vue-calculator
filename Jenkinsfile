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
                echo 'Install dependencies! develop'
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    sh 'npm install'
                }
            }
        }
    }
}
