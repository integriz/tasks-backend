pipeline {
    agent any

    stages {
        stage('Build Backend') {
            steps {
                bat 'mvn clean package -DskipTests=true'
            }
        }
        stage('Unit Tests') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Sonar analysis') {
            environment{
                scannerHome = toll 'SONAR_SCANNER'
            }
            steps{
            	withSonarQubeEnv('SONAR_LOCL'){
            		bat "${scannerHome}/bin/sonar-scanner -e -Dsonar.projectKey=DeployBack -Dsonar.host.url=http://192.168.99.100:9000 -Dsonar.login=6df85c6dcab2e1216eea2e87c05f8664fbd54f0a -Dsonar.java.binaries=target -Dsonar.coverage.exclusions=**/.mvn/**,**/src/test/**,**/model/**,**Application.java"
            	}
             }
		}
    }
}
