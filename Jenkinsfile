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
                running_process=`ps -ef|grep helloworld-job_master|grep -v grep|awk \'{print $2}\'`;
                if [ -n "$running_process" ]
				then
				  kill $running_process;
				fi  
                JENKINS_NODE_COOKIE=dontKillMe /tmp/spring_boot.sh
                '''
            }
        }
    }
}
