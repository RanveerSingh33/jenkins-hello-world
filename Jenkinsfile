pipeline {

    agent any

    tools {
        maven "M398"
    }

    stages {

        stage('Echo Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn --version'
            }
        }

        stage('Build') {
            steps {

                // Repository already cloned by Jenkins SCM
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {

                script {

                    for (int i = 0; i < 60; i++) {
                        echo "${i + 1}"
                        sleep 1
                    }
                }

                sh 'mvn test'
            }
        }
    }
}
