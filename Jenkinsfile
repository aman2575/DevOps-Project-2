pipeline {
    agent { label 'Jenkins-Slave' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }
        }
        stage(" Checkout from SCM "){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/aman2575/DevOps-Project-2'
            }
        }
        stage(" Build Application "){
            steps {
                sh "mvn clean packages"
            }
        }
        stage(" Test Application "){
            steps{
                sh "mvn test"
            }
        }
    }
}
 