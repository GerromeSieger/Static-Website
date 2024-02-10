pipeline {
  agent any
  triggers {
    githubPush()
  }
  stages {
    stage('Build') { 
      agent any
      steps {
        sh 'echo yarn installm' 
        sh 'echo yarn build' 
      }
    }

    stage('Test') {
      agent any
      steps {
        sh 'echo pip install -r requirements.txt'
        sh 'echo pytest tests/'
      }
    }

    stage('Deploy') {
      agent any 
      steps {
        withCredentials([sshUserPrivateKey(credentialsId: 'remote-server-cred', keyFileVariable: 'SSH_PRIVATE_KEY', usernameVariable: 'REMOTE_USER')]) {
          script {
            sshCommand remote: [
              name: 'ec2server',
              host: '34.203.205.58',
              user: env.REMOTE_USER,
              keyFile: env.SSH_PRIVATE_KEY
            ], command: 'sudo apt update'
          }
        }
    }
  }
}
}
