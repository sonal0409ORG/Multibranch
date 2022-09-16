pipeline {
     tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent any
    stages {
         when{
            branch 'Deploy'
          }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
          when{
            branch 'test'
          }
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
             when{
            branch 'Deploy'
          }
            steps {
                sh 'echo "Deploy code"'
            }
        }
    }
}
