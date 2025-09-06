pipeline {
    agent {
       label 'docker'
    }
 
    stages {
         
         stage('build from a docker file'){
            steps {
                 script {
                     sh 'docker build -t nerosegnofic/react-test -f Dockerfile.dev .'
                 }
 
            }
 
         }
 
            stage('run those tests'){
              steps {
 
                    script {
 
                        env.DOCKER_BUILDKIT = 1
                        sh 'docker run -e CI=true nerosegnofic/react-test npm run test'
                    }
 
              }
            }
 
    }
}