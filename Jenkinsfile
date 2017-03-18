pipeline {
    agent any
    tools {
        maven 'Maven 3.3.9'
        jdk 'jdk8'
    }


    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo password is ${PASSWORD}
                    mvn package
                '''
            }
        }

        stage ('Build') {
            steps {
                echo 'This is a minimal pipeline.'
            }
        }
    }
}