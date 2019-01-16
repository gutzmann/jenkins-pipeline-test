pipeline {
    agent none
    triggers { pollSCM('* * * * *') }
    stages {
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
        stage('Sequential') {
            environment {
                FOR_SEQUENTIAL = "some-value"
            }
            stages {
                stage('In Sequential 1') {
                    steps {
                        echo "In Sequential 1"
                    }
                }
                stage('In Sequential 2') {
                    steps {
                        echo "In Sequential 2"
                    }
                }
                stage('Parallel In Sequential') {
                    parallel {
                        stage('In Parallel 1') {
                            steps {
                                echo "In Parallel 1"
                            }
                        }
                        stage('In Parallel 2') {
                            steps {
                                echo "In Parallel 2"
                            }
                        }
                    }
                }
            }
        }
    }
}
