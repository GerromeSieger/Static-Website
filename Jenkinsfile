pipeline {
  agent any
  triggers {
    githubPush()
  }
  stages {
    stage ('Deploy') {
        steps{
            withCredentials([sshUserPrivateKey(credentialsId: 'remote-server-cred', keyFileVariable: 'SSH_PRIVATE_KEY')]) {
                sh 'ssh -o StrictHostKeyChecking=no -i ${SSH_PRIVATE_KEY} ubuntu@54.147.13.163 "whoami"'
            }
        }
    }
}
}