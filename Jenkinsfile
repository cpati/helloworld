pipeline {
    agent any
    

    stages {
        stage('Build') {
            steps {
            		sh '''
                 mvn clean install;
                 '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                mvn test
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                JENKINS_NODE_COOKIE=dontKillMe /tmp/spring_boot.sh
                '''
            }
        }
    }
}
