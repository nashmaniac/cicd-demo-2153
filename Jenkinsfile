pipeline {
    agent any
    environment {
        DOCKER_IMAGE_TAG = "my-app:build-${env.BUILD_ID}"
    }
    stages {
        stage('Initialize'){
            def dockerHome = tool 'myDocker'
            env.PATH = "${dockerHome}/bin:${env.PATH}"
        }
        stage('Build') {
            steps {
                script {
                    docker_image = docker.build("${env.DOCKER_IMAGE_TAG}", '-f ./Dockerfile .')
                }
            }
        }
//         stage('Build') {
//             steps {
//                 echo 'Building..'
//                 sh 'docker build . -t hello-world'
//             }
//         }

        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}