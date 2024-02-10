pipeline {
  agent any
  triggers {
    githubPush()
  }
  stages {
    stage('Deploy') {
      agent any 
      steps {
        withCredentials([sshUserPrivateKey(credentialsId: 'remote-server-cred', keyFileVariable: 'SSH_PRIVATE_KEY', usernameVariable: 'REMOTE_USER')]) {
          script {
            sshCommand remote: [
              name: 'ec2server',
              host: '54.147.13.163',
              user: 'ubuntu',
              identiy: ${SSH_PRIVATE_KEY},
              allowAnyHosts: true
            ], command: "whoami"
          }
        }
    }
  }
}
}