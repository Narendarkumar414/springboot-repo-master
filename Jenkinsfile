pipeline {
    agent any
    stages {
        stage('list repo files') {
            steps {
                script {
                    sh "ls"
                }
            }
        }
        stage('show working directory') {
            steps {
                script {
                    sh "pwd"
                }
            }
        }
        stage('creating build') {
            steps {
                script {
                    sh "./gradlew clean build"
                }
            }
        }
        stage('list build contents') {
            steps {
                script {
                    sh "ls build/libs"
                }
            }
        }
        stage('copy buid file to docker build context') {
            steps {
                script {
                    sh "sudo cp /build/libs/spring-boot-with-prometheus-0.1.0.jar DOCKER/"
                }
            }
        }
    }
}
