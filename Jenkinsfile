pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        sh 'ssh -i /tmp/health-couch.pem cloud-health-couch.com.au \'cd health-couch-deploy && git pull && docker-compose pull && docker-compose up -d\''
      }
    }

  }
}