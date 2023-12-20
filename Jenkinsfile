pipeline {
    
    agent none
           
    stages {
        stage('Git Clone') { 
           agent any
            steps {
                echo " Git Cloning"
                git 'https://github.com/mrobel/maven-web-app.git'
            }
        }
        stage('Ansible Playbook') {
           agent {
             label 'Ansible-CN'
           } 
            steps {
              sh "ansible-playbook playbook.yml"
            }
        }
    }
}
