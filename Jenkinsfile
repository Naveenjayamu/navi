pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build your code here
                sh 'mvn clean install'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests here
                sh 'mvn test'
            }
            post {
                always {
                    // Archive test reports
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your application here
                sh 'mvn deploy'
            }
        }
    }
}
