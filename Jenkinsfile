pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven-3"
    }

    stages {
        stage('Clean') {
            steps {
                cleanWs()
            }    
        }
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/mpelnikowski/szkolenie-cicd-jenkins-gitlab-example.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean verify'
                //slackSend 'Build Started - ${env.BUILD_TAG} ${env.BUILD_NUMBER}'
            }    
        }
    }
    
}
