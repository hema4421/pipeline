pipeline {
     agent any
         stages {
             stage('Build') {
                 steps {
                     echo 'Application is in Building Phase'
                     bat 'mvn clean install'
                     }
                 }
             stage('Test') {
                 steps {
                     echo 'Application is in Testing Phase'
                     bat 'mvn test'
                       }
                 }
                 stage('Deploy CloudHub') { 
                     environment {
                         ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
                                   }
                   steps {
                    sh 'mvn deploy -P cloudhub -Dmule.version=4.3.0 -Danypoint.username=login-12 -Danypoint.password=Hemala03' 
                          }
                    }
         }
     }
