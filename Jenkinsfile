node('docker') {
    def customImage
    
    stage('clone repositories') {
        checkout scm
    }

    stage('Build Image') {
        customImage = docker.build("rohitashpathak89/dockeragent:${env.BUILD_ID}")
    }

    stage('Push the Image') {
        docker.withRegistry('https://registry.hub.docker.com/', 'DockerHub') {
        /* Push the container to the custom Registry */
            customImage.push()
    }
    echo "Trying to Push Docker Build to DockerHub"
    }
}