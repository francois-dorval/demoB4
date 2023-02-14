pipeline {
    agent any

    tools {
        jdk "jdk11"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/francois-dorval/demoB4.git'

                sh "./gradlew clean test"

            }

            post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    junit 'build/test-results/test/*.xml'
                }
            }
        }
    }
}
