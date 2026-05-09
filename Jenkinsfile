pipeline {

    agent any

    tools {
        // Maven configured in Jenkins
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

                // Clone GitHub repository
                //git branch: 'main', url: 'https://github.com/RanveerSingh33/jenkins-hello-world'

                // Build Maven package
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {
               for (int i = 0; i < 60; i++) {
                  echo "${i + 1}"
                  sleep 1
                 }
                
                // Run Maven tests
                sh 'mvn test'
            }
        }
    }
}
