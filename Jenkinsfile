pipeline {
    agent any 
    stages {
        node('mac') {
            stage('Reinitialize jenkins keychain') {
                steps {
                    sh "./fastlane refreshJenkinsKeychain"
                }
            }
        }
 node('mac') {
        stage('Populate Jenkins Keychain') {
            steps {
                sh "./fastlane matchPopulateJenkinsKeychain"
            }
        }
 }
 node('mac') {
        stage('Build application for beta') {
            steps {
                sh "./fastlane buildAppWithGym"
            }
        }
    }
}