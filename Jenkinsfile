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
                sh 'npm install'
            }
        }
    }
}

// https://www.jenkins.io/doc/tutorials/build-a-node-js-and-react-app-with-npm/