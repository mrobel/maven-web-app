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
        stage('Build Project') {
            steps {
               sh 'mvn clean package'
            }
        }
        
        stage('Ansible Playbook for Image & Deployment in K8s') {
            steps{
                sh 'ansible-playbook task.yml'
                }
        }
    }
}
