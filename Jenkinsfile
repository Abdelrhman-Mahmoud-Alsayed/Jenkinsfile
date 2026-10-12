pipeline {
  agent any
  parameters {
    choice(name: 'ENVIRONMENT', choices: ['dev', 'prod','stg'])
  }
  stages {
    stage('Deploy') {
      steps {
        sh "chmod +x hello.sh"
        sh "./hello.sh ${params.ENVIRONMENT}"
      }
    }
    stage('run') {
      steps {
        sh 'chmod +x hello.sh'
        sh './hello.sh'
  }
}
    
