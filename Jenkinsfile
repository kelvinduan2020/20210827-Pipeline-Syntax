pipeline {
    agent none 
    stages {
        stage('Agent from Docker') {
            agent { 
                docker {
                    image 'maven:3.8.1-adoptopenjdk-11'
                    args  '-v /tmp:/tmp'
                }
            } 
            steps {
                echo 'Hello, Maven'
                sh 'mvn --version'
            }
        }
        stage('Agent from Dockerfile') {
            agent {
                dockerfile {
                    filename 'Dockerfile.build'
                    dir 'buildDockerfile'
                    additionalBuildArgs '--build-arg version=1.0.0'
                    args '-v /tmp:/tmp'
                    //registryUrl 'https://myregistry.com/'
                    //registryCredentialsId 'myPredefinedCredentialsInJenkins'
                }
            }
            steps {
                echo 'Hello, Ubuntu'
                sh 'ls -l'
            }
        }
    }
}
