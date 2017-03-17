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
                    cf login -a api.run.pivotal.io -p ${PASSWORD} -u daliu@pivotal.io -o verydapeng.com -s dev
                    cf a
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