pipeline {
    agent any

      tools { 
        maven 'Maven-3' 
        jdk 'Java-8' 
       }

      stages {

       stage ('Initialize the build variables') {
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
                sh 'cd integration-testing && mvn clean verify -P integration-test'
                 }
        }
       stage('Docker image build') {
            steps {
                echo '..... Copying Artifacts & Building Docker image :: ......'
                sh 'cp java_web_code/target/wildfly-spring-boot-sample-1.0.0.war docker'
                sh 'cd docker && sudo docker build -t devops_pipeline_demo .'
                 }
        }
              
        
    }
}
