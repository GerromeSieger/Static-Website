pipeline {
  agent any
  environment {
    IP_CRED = credentials('ssh-key') 
  }  
  triggers {
    githubPush()
  }
  stages {
    stage ('Deploy') {
        steps{
            withCredentials([sshUserPrivateKey(credentialsId: 'remote-server-cred', keyFileVariable: 'SSH_PRIVATE_KEY', usernameVariable: 'REMOTE_USER')]) {
            sh """
            ssh -o StrictHostKeyChecking=no -i ${SSH_PRIVATE_KEY} ${REMOTE_USER}@${IP_CRED} <<EOF
            whoami
            pwd
            ls -al
           EOF
            """
            }
        }
    }
}
}