pipeline {
    agent any

    environment {
        DOCKER_REGISTRY_CREDENTIALS = credentials('your-credentials-id')
    }

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
        stage('Build Docker Image') {
            steps {
                // Build Docker image with tag
                script {
                    docker.withRegistry('https://hub.docker.com/repository/docker/nguyennam140401', 'vue-admin-element') {
                        def dockerImage = docker.build("nguyennam140401/vue-element-admin:${env.BUILD_NUMBER}")
                        dockerImage.push()
                    }
                }
            }
        }
    }
}
