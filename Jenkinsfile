pipeline {
  agent any
  environment {
    EC2 = credentials('health-couch')
  }
  stages {
    stage('Deploy') {
      steps {
        sh 'printenv'
        sh "chmod 600 ${EC2}"
        sh "ssh -i ${EC2} ubuntu@cloud.health-couch.com.au \'cd health-couch-deploy && git pull && docker-compose pull && docker-compose up -d\'"
      }
    }

  }
}