Pipeline {
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
        
        stage('Agent From Dockerfile') {
            agent {
                dockerfile {
                    filename 'Dockerfile.build'
                    dir 'buildDockerfile'
                    label 'dockerfile-agent'
                    additionalBuildArgs '--build-arg version=1.0.0'
                    args '-v /tmp:/tmp'
                    //registryUrl 'https://myregistry.com/'
                    //registryCredentialsId 'myPredefinedCredentialsInJenkins'
                }
                steps {
                    echo 'Hello, Nginx'
                    sh 'sudo systemctl status nginx'
                }
            }
        }
    }
    
    
    
  
}
