pipeline {
  agent any
  stages {
    stage('Dev Deployment') {
      steps {
        retry(x) { // It Retries x number of times mentioned until its successful
          sh './dev-deploy.sh'
        }
        timeout(time: x, unit: 'MINUTES') { // Time out option will make the step wait for x mins to execute if it takes more than that it will fail
          sh './readiness-check.sh'
        }
      }
    }
  }
}
