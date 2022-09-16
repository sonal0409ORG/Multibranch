pipeline {
    agent any
    stages {
        stage('Build') {
          when {
            branch 'Deploy'
          }
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
          
           when {
            branch 'Deploy'
          }
            steps {
                sh 'echo "deploy demo"'
            }
        }
    }
}
