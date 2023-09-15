pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven-3"
    }

    stages {
        stage('Build') {
            when {
                not {
                    changelog '.*^\\[ci skip\\] .+$'
                }
            }
            steps {
                git branch: 'main', url: 'https://github.com/mpelnikowski/szkolenie-cicd-jenkins-gitlab-example.git'
                sh 'mvn clean verify'
                cleanWs()
            }    
        }
    }  
}
