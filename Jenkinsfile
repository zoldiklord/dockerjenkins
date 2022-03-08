node {
    def app 
        stage('Clone') {
                checkout scm 
        }
        stage('Build image) {
                app = docker.build("hamza/nginx")
        }
        stage('Run image') {
                docker.image('hamza/nginx').withRun('-p 80:80') { c ->
                sh 'docker ps'
        }
}
