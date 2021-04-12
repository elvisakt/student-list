pipeline {
    agent any

    environment {
        imagename = "elvis061998/4dvop-simple_api"
        
            }

    stages {
        stage('Build') {
            steps {
               
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
