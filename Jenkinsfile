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
               ansiblePlaybook become: true, credentialsId: 'Slave-credential', disableHostKeyChecking: true, installation: 'Ansible-CN', inventory: '/etc/ansible/hosts', playbook: '/home/ansible/play.yml', vaultTmpPath: ''
            }
    }
}
