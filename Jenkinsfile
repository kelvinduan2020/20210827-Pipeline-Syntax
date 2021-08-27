pipeline {
    agent none
    
    //Stage-level Agent Section
    stages {        
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
            }
            steps {
                echo 'Hello, Nginx'
                sh 'sudo systemctl status nginx'
            }
        }
    }
}
