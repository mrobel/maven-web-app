pipeline {
    
    agent any
    
        tools {
                maven "Maven-3.9.4"
        } 
    stages {
        stage('Git Clone') {    
            steps {
                echo " Git Cloning"
                git 'https://github.com/mrobel/maven-web-app.git'
            }
        }
        stage('Maven Build') {
            steps {
                echo "Build Project"
                sh "mvn clean package"
            }
        }
    }
}
