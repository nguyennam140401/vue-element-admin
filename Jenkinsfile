pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'cat Dockerfile'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'Hello World 2'
            }
        }
    }
}
