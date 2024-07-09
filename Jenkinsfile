node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/jyong8/jenkins-mydiary-msa.git/'
    }

    stage('Build image') {
       dockerImage = docker.build("jyong12/mydiary:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
