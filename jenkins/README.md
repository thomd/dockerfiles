# Jenkins

Jenkins based on `jenkins/jenkis_alpine` with nodejs installed.

# Run

    docker pull thomd/jenkins
    docker run -d --name jenkins -p 8080:8080 -v ~/.jenkins:/var/jenkins_home thomd/jenkins
    docker logs -ft jenkins
