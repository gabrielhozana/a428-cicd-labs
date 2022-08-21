pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim'
            args '-p 49001:49001'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm config rm proxy'
                sh 'npm config rm https-proxy'
                sh 'npm config set registry http://registry.npmjs.org/'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}

// https://www.jenkins.io/doc/tutorials/build-a-node-js-and-react-app-with-npm/