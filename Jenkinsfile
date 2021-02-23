node('docker') {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com/', 'DockerHub') {
        /* below command will build the image under rohitashpathak89 account in repo dockeragent
        and tag with the build number */

        def customImage = docker.build("rohitashpathak89/dockeragent:${env.BUILD_ID}")

        /* Push the container to the custom Registry */
        customImage.push()
    }
    echo "Trying to Push Docker Build to DockerHub"
}