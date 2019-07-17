pipeline {
    agent any

      stages {
        stage('Building the app') {
            steps {
                echo '..... Build Phase Started :: Compiling Source Code :: ......'
                sh cd java_web_code
                sh 'mvn install'
            }
        }
        stage('Testcases execution') {
            steps {
                echo '..... Test Phase Started :: Testing via Automated Scripts :: ......'
                sh cd ../integration-testing/
                sh mvn clean verify -P integration-test
                sh 'ansible-playbook site.yml -i inventory/hosts -f 5 -e provider=${Cloud_Provider} -e region=${aws_region} -e tf_state=${Terraform_State} -e instance_name=${Instance_Name} --check'
            }
        }
        stage('Creating the image') {
            steps {
                echo 'Excecuting a dry run..'
                sh 'ansible-playbook site.yml -i inventory/hosts -f 5 -e provider=${Cloud_Provider} -e region=${aws_region} -e tf_state=${Terraform_State} -e instance_name=${Instance_Name} --check'
            }
        }
        stage('Creating the image') {
            steps {
                echo 'Excecuting a dry run..'
                sh 'ansible-playbook site.yml -i inventory/hosts -f 5 -e provider=${Cloud_Provider} -e region=${aws_region} -e tf_state=${Terraform_State} -e instance_name=${Instance_Name} --check'
            }
        }
        stage('Creating the image') {
            steps {
                echo 'Excecuting a dry run..'
                sh 'ansible-playbook site.yml -i inventory/hosts -f 5 -e provider=${Cloud_Provider} -e region=${aws_region} -e tf_state=${Terraform_State} -e instance_name=${Instance_Name} --check'
            }
        }
        
        
    }
}
