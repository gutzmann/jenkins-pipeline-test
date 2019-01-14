pipeline {
    agent  none
    stage('maven') {
        agent {
            docker {
                image 'maven:3.3.3'
            }
        }

        steps {
            sh 'mvn --version'
            sh 'java -version'
        }
    }

    stage('build') {
        agent { docker { image 'node:6.3' } }
        steps {
            sh 'npm --version'
        }

    }
    agent { docker { image 'python:3.5.1' } }
    stage('build') {
        agent { docker { image 'python:3.5.1' } }
        steps {
            sh 'python --version'
        }
    }

}
