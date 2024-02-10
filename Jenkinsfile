pipeline {
  agent any
  triggers {
    githubPush()
  }
  stages {
    stage ('Deploy') {
        steps{
            sshagent(credentials : ['ssh-key']) {
                sh 'ssh -o StrictHostKeyChecking=no ubuntu@54.147.13.163 "whoami"'
            }
        }
    }
}
}