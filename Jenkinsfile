pipeline {
    agent any

    stages {
        stage('Início') {
            steps {
                bat 'echo Início'
            }
        }
        stage('Meio') {
            steps {
                bat 'echo Meio'
                bat 'echo Meio de novo'
            }
        }
        stage('Fim') {
            steps {
                sleep(5)
                bat 'echo Fim'
            }
        }
    }
}
