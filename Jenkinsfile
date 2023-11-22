pipeline {
    agent any
    environment {
        YOUR_NAME = credentials("YOUR_NAME")
    }
  
    stages {
        stage('Build') {
            steps {
                sh '''
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
                kubectl apply -f .
                sleep 60
                kubectl get services
                '''
            }

        }

    }

}

