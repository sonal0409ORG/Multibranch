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
                sh 'mvn clean package'
            }
        }
        stage('Test') {
          when{
            branch 'test'
          }
            steps {
                sh 'mvn test'
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
