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
              host: '34.203.205.58',
              user: REMOTE_USER,
              identiyFile: SSH_PRIVATE_KEY,
              allowAnyHosts: true
            ], command: "whoami"
          }
        }
    }
  }
}
}