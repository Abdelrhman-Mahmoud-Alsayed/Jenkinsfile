
pipeline {
    agent any

    stages {
        stage('Hello World') {
            steps {
                echo 'Hello Wrld'
            }
        }
   

        stage('Run Script') {
            steps {
                sh '''
                    chmod +x hello.sh
                    ./hello.sh
                '''
            }
        }
    }

    post {
        always {
            ech 'Pipeline finished (success, failure, or aborted).'
        }

        success {
            echo 'Pipeline executed successfully!'
        }

        failure {
        emailext(
            to: 'abdelrhman9004@gmail.com',
            subject: "Pipeline Failed: ${env.JOB_NAME}",
            body: "Build failed! Check: ${env.BUILD_URL}"
        )
    
        }

        aborted {
            echo 'Pipeline was aborted!'
        }
    }

}
