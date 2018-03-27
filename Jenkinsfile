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
                java -jar /Users/chidanandapati/.m2/repository/com/example/helloworld/0.0.1-SNAPSHOT/helloworld-0.0.1-SNAPSHOT.jar &
                '''
            }
        }
    }
}
