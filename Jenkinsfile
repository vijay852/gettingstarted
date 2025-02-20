pipeline {
    agent any
    environment {
        DOCKER_TAG = getDockerTag()
    }
      stages{
            stage('Checkout SCM') {
            steps {
                // This step checks out your Git repository
               git branch: 'main', credentialsId: 'eb780d03-dc76-426e-8a56-54c12392746c', url: 'https://github.com/vijay852/gettingstarted.git'
                  }
            }
         stage("Build Docker Image"){
            steps{
                sh "docker build -t vijay4444/nodeapp:${DOCKER_TAG}"
            }
         }
      }
}

def getDockerTag()
{
    def tag = sh script: 'git rev-parse HEAD', returnStdout: true
    return tag
}