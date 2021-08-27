pipeline {
    agent none 
    stages {
        stage('Example Build') {
            agent { 
                docker {
                    image 'maven:3.8.1-adoptopenjdk-11'
                    label 'maven-agent'
                    args  '-v /tmp:/tmp'
                }
            } 
            steps {
                echo 'Hello, Maven'
                sh 'mvn --version'
            }
        }
        stage('Example Test') {
            agent { docker 'openjdk:8-jre' } 
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}
