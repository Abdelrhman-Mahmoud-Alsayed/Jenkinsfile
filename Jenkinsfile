
pipeline {
    agent any

    stages {
        stage('Hello World') {
            steps {
                echo 'Hello Wrld'
            }
        }
            post {
    failure {
        emailext(
            to: 'your-email@gmail.com',
            subject: "Pipeline Failed: ${env.JOB_NAME}",
            body: "Build failed! Check: ${env.BUILD_URL}"
        )
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
            echo 'Pipeline finished (success, failure, or aborted).'
        }

        success {
            echo 'Pipeline executed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }

        aborted {
            echo 'Pipeline was aborted!'
        }
    }

}
