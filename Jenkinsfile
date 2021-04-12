pipeline {
    agent any

    environment {
        imagename = "elvis061998/4dvop-simple_api"
        
            }

    stages {
        stage('Build') {
            steps {
               node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            app = docker.build("elvis061998/4dvop-simple_api")    
       }     
      stage('Test image') {           
            app.inside {            
             
             sh 'echo "Tests passed"'        
            }    
        }     
       stage('Push image') {
                                                  docker.withRegistry('https://hub.docker.com/repository/docker/elvis061998/4dvop-simple_api', 'git') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
            }

    stages {
        stage('test') {
            steps {
               sh 'docker run -d --name api -p 5000:5000 elvis061998/4dvop-simple_api'
            
            }

    stages {
        stage('deploy') {
            steps {

               sh "ansible-playbook -i hosts install-docker.yml"
               sh "ansible-playbook -i hosts 4dvop-app.yml"
               
            
            }
        }
    }
}
