pipeline {
    agent any

    tools {
        nodejs 'nodejs-24-1-0'
    }
    
    stages{
        stage('VM node Version') {
            steps {
                sh '''
                    node -v
                    npm -v
                '''
            }
        }
    }
}
