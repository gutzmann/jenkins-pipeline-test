pipeline {
    agent none
    triggers { pollSCM('* * * * *') }
    stages {
        stage('get versions from docker')
        parallel {
            stage('maven') {
                agent {
                    docker { image 'maven:3.3.3' }
                }

                steps {
                    sh 'mvn --version'
                    sh 'java -version'
                }
            }

            stage('npm') {
                agent { docker { image 'node:6.3' } }
                steps {
                    sh 'npm --version'
                    sh 'node --version'
                }

            }
            stage('python') {
                agent { docker { image 'python:3.5.1' } }
                steps {
                    sh 'python --version'
                }
            }
        }

    }
}
