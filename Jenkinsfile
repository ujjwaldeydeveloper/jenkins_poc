pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                cleanWs()
                checkout scm
            }
        }
        stage('Dependency added') {
            steps {
                withEnv([]) {
                    sh 'flutter pub get'
                }
            }
        }
        stage('Build APK') {
            steps {
                withEnv([]) {
                    sh 'flutter build apk'
                }
            }
        }
    }
}