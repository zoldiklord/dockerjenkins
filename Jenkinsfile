pipeline {
        agent any
     stages {
        stage('Clone') {
             steps {
                checkout scm 
        }}
        stage('Build image') {
              steps {
        script {
                docker.build("hamza/nginx")
        }}}
        stage('Run image') {
              steps {
                script {
                docker.image('hamza/nginx').withRun('-p 80:80') { c ->
                sh 'docker ps'
                }}
        }
}
stage( 'Deploy') {
  steps {
    script {
      docker.withRegistry(
         'https://710245512785.dkr.ecr.us-east-1.amazonaws.com',
         'ecr:myawscredentials') {
         def myImage
         myImage.push('1.0')
         docker.build('docker-image')
}}}}}}
