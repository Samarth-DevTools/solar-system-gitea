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

        stage('Dependency Scanning') {
            parallel {
                stage('NPM Dep Audit') {
                    steps {
                        sh '''
                            npm audit --audit-level=critical
                            echo $?
                        '''
                    }
                }
                stage('OWASP Dep check') {
                    steps {
                        dependencyCheck additionalArguments: '''
                            --scan \\\'./\\\'
                            --out \\\'./\\\'
                            --format \\\'ALL\\\'
                            --prettyPrint''', odcInstallation: 'OWASP-depcheck-10'
                        }      
                    } 
                }
            }
        }
    }
}

