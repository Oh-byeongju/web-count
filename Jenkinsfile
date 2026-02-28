node {
    stage('Clone repository') {
        git branch: 'main', credentialsId: 'github_access_token', url: 'https://github.com/Oh-byeongju/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("neda3/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
