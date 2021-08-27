pipeline {
    agent {
        docker 'maven:3.8.1-adoptopenjdk-11'
        label 'docker-agent'
        args  '-v /tmp:/tmp'
    }
    
    stages {        
        stage('Agent From Docker') {
            steps {
                echo 'Hello, Maven'
                sh 'mvn --version'
            }
        }
    }
}
