pipeline {
    agent any

    stages {
        stage('test') {
            steps {
                sh './gradlew test'
            }
        }
        stage('build jar') {
            steps {
                sh './gradlew build -x test'
            }
        }
        stage('load to remote server') {
            steps {
                sshagent(credentials : ['metech-ssh']) {
                    sh "scp -o StrictHostKeyChecking=no ./build/libs/link-shortener-${tag}.jar metech@195.93.252.91:./link-shortener/link-shortener.jar"
                }
            }
        }
    }
}