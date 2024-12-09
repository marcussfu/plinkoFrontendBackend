pipeline {
    agent any

    environment {
        DOCKER_COMPOSE_PATH = "./docker-compose.yml"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/your-username/your-repo.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                script {
                    dockerComposeBuild()
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    dockerComposeUp('-d')
                    // Run your tests here, for example:
                    // sh 'docker-compose exec backend npm run test'
                    // sh 'docker-compose exec frontend npm run test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add your deployment steps here
                    dockerComposeDown()
                    dockerComposeUp('-d')
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}

def dockerComposeBuild() {
    sh "docker-compose -f ${env.DOCKER_COMPOSE_PATH} build"
}

def dockerComposeUp(options = '') {
    sh "docker-compose -f ${env.DOCKER_COMPOSE_PATH} up ${options}"
}

def dockerComposeDown() {
    sh "docker-compose -f ${env.DOCKER_COMPOSE_PATH} down"
}
