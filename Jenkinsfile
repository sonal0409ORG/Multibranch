pipeline {
     tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent any
    stages {
         
        stage('Build') {
             when{
            branch 'Deploy'
          }
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
