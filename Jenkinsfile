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
                            bat 'mvn clean package deploy -DmuleDeploy -DmuleVersion=4.3.0 -Dusername=login-12 -Dpassword=Hemala03 -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
                         }
                    }
         }
     }
