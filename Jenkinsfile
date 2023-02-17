pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                
                sh 'g++ -o PES1UG20CS671 PES1UG20CS671.cpp'
                build job: 'PES1UG20CS671-1'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './PES1UG20CS671'
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
            steps {
                
                sh "chmod +x -R ${env.WORKSPACE}"
                echo 'Deployment Successful'
            }
        }
    }

    post {
      failure{
        echo 'Pipeline failed'
      }
        
    }
}
