pipeline {
  agent any
  environment {
    EC2 = credentials('health-couch')
  }
  stages {
    stage('Deploy') {
      steps {
        sh 'printenv'
        sh 'ssh -i /tmp/health-couch.pem cloud.health-couch.com.au \'cd health-couch-deploy && git pull && docker-compose pull && docker-compose up -d\''
      }
    }

  }
}