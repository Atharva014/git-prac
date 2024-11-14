pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven-3.9.9"
    }

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/jenkins-docs/simple-java-maven-app.git'

                
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'

            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'

            }
            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deplolyed'

            }
        }

    }
    post {
        failure {
            echo "Failure!!!"
        }
        success {

        }
    }
}
