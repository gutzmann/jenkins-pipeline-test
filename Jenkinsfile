pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('maven') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('java') {
                    steps {
                        sh 'java -version'
                    }
                }
    }
}