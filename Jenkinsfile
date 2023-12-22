pipeline {
  
    agent {
        label 'Ansible-CN'
    }
    
    tools{
        maven "Maven-3.9.6"
    }

    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/mrobel/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        
        stage('Create Image') {
            steps{
                sh 'ansible-playbook task.yml'
                }
        }
    }
}
