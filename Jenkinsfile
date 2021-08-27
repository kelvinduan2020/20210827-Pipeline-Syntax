pipeline {
    agent none
    
    //Stage-level Agent Section
    stages {        
        stage('Agent From Docker') {
            agent {
                docker 'maven:3.8.1-adoptopenjdk-11'
                label 'docker-agent'
                reuseNode true
            }
            steps {
                echo 'Hello, Maven'
                sh 'mvn --version'
            }
        }
    }
}
