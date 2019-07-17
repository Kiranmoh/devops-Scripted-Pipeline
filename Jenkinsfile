pipeline {
    agent any

      stages {
        stage('Building the app') {
            steps {
                echo '..... Build Phase Started :: Compiling Source Code :: ......'
                sh 'cd java_web_code && mvn install'
                }
        }
        stage('Testcases execution') {
            steps {
                echo '..... Test Phase Started :: Testing via Automated Scripts :: ......'
                sh 'cd ../integration-testing/'
                sh 'mvn clean verify -P integration-test'
            }
        }
              
        
    }
}
