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
              ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'Ansible-CN', inventory: '/etc/ansible/hosts', playbook: '/etc/ansible/play.yml', vaultTmpPath: ''
            }
        }
    }
}
