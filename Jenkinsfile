pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stage {
        stage ("Cleanup Workspace"){
            steps {
                cleanWs()
            }
        }
        stage(" Checkout from SCM "){
            steps {
                git branch: 'main', credentialsID: 'github', url: 'https://github.com/aman2575/DevOps-Project-2'
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
 