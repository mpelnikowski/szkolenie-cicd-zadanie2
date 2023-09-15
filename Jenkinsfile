pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven-3"
    }

    stages {
        stage('Build') {

            steps {
                //sh 'mvn -version'
                git branch: 'main', url: 'https://github.com/mpelnikowski/szkolenie-cicd-jenkins-gitlab-example.git'
                sh 'chmod a+x /var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3'
                sh 'mvn clean spring-boot:build-image'
                cleanWs()
            }    
        }
    }  
}
