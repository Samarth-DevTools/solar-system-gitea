pipeline {
    agent any

    tools {
        nodejs 'nodejs-24-1-0'
    }

    stages{
        stage('Installing Deps') {
            steps {
                sh 'npm install --no-audit'
            }
        }
    }
}
