pipeline {
  agent none 
  triggers {
    githubPush()
  }
  stages {
    stage('Build') { 
      agent {
        docker { image 'node:18-alpine' }  
      }
      steps {
        sh 'echo npm install' 
        sh 'echo npm run build' 
      }
    }

    stage('Test') {
      agent { 
        docker { image 'python:3.7-alpine' }  
      }
      steps {
        sh 'echo pip install -r requirements.txt'
        sh 'echo pytest tests/'
      }
    }

    stage('Deploy') {
      agent any 
      steps {
        sh 'echo ansible-playbook playbooks/deploy.yml'  
      }
    }
  }
}
