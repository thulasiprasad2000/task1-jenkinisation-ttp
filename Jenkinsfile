pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                echo 'this is test message from Thulasi from jenkinsfile'
                docker build -t thulasiprasad2000/task1jenk .
                '''
            }

        }
        stage('Push') {
            steps {
                sh '''
                docker push thulasiprasad2000/task1jenk
                '''
            }

        }
        stage('Deploy') {
            steps {
                sh '''
                docker stop task1 && echo "stopped task1" || echo "task1 is not running"
                docker rm task1 && echo "removed tasks1" || echo "task1 doesnot exist"
                docker run -d -p 80:5500 --name task1 thulasiprasad2000/task1jenk
                '''
            }

        }

    }

}

