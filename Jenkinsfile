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
                BUILD_ID=dontKillMe BUILD_ID=dontKillMe nohup bash /tmp/spring_boot.sh &
                '''
            }
        }
    }
}
