pipeline {
  agent any
  parameters {
    choice(name: 'ENVIRONMENT', choices: ['dev', 'prod','stg'])
  }
  stages {
    stage('Deploy') {
      steps {
        sh "echo Deploying to ${params.ENV}"
        sh "./deploy.sh ${params.ENV}"
      }
    }
  }
}
    
