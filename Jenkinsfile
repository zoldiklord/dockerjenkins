pipeline {
    def app 
        stage('Clone') {
                checkout scm 
        }
        stage('Build image') {
                app = docker.build("hamza/nginx")
        }
        stage('Run image') {
                docker.image('hamza/nginx').withRun('-p 80:80') { c ->
                sh 'docker ps'
                
        }
}
stage( 'Deploy') {
  steps {
    script {
      docker.withRegistry(
         'https://710245512785.dkr.ecr.us-east-1.amazonaws.com',
         'ecr:docker-image:myawscredentials') {
         def myImage
         myImage.push('1.0')
                         docker.build('docker-image')
}}}}}
