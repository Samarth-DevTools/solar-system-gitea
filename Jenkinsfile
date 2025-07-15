pipeline {
    agent any

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
