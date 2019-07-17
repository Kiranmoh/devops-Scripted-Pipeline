pipeline {
    agent any

      stages {
        stage('Building the app') {
            steps {
                echo '..... Build Phase Started :: Compiling Source Code :: ......'
                bat 'set M2_HOME=C:/Kiran/Maven/apache-maven-3.6.1'
                bat 'set PATH=%M2_HOME%/bin'
                bat 'cd java_web_code'
                bat 'mvn install'
            }
        }
        stage('Testcases execution') {
            steps {
                echo '..... Test Phase Started :: Testing via Automated Scripts :: ......'
                bat 'cd ../integration-testing/'
                bat 'mvn clean verify -P integration-test'
            }
        }
              
        
    }
}
