pipeline {
    agent any
    parameters {
        string(name: 'tag_version', defaultValue: '$BUILD_NUMBER', description: 'release date buildno')
    }
    stages {
        stage('Declare') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('Pre-Build') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
