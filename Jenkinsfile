pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                cleanWs()
                checkout scm
            }
        }
        stage('Pre-Build') {
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
        stage('ArchieveApkAndroid') {
            steps {
                archiveArtifacts artifacts: '/build/app/outputs/flutter-apk/app-release.apk', fingerprint: true, onlyIfSuccessful: true
            }
        }
    }
}