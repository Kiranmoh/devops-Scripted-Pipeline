pipeline {
    agent any

      tools { 
        maven 'Maven-3' 
        jdk 'Java-8' 
       }

      stages {

       stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        stage('Building the app') {
            steps {
                echo '..... Build Phase Started :: Compiling Source Code :: ......'
                sh 'cd java_web_code && mvn install'
                }
        }
        stage('Testcases execution') {
            steps {
                echo '..... Test Phase Started :: Testing via Automated Scripts :: ......'
                sh '''
                    cd ../integration-testing/
                    mvn clean verify -P integration-test
                '''
                  }
        }
              
        
    }
}
