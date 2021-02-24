pipeline {
    agent any 
    stages {
        stage('Reinitialize jenkins keychain') {
            steps {
                node('mac') {
                    sh "./fastlane refreshJenkinsKeychain"
                }
            }
        }
        stage('Populate Jenkins Keychain') {
            steps {
                node('mac') {
                    sh "./fastlane matchPopulateJenkinsKeychain"
                }
            }
        }
        stage('Build application for beta') {       
            steps {
                node('mac') {
                    sh "./fastlane buildAppWithGym"
                }
            }
        }
    }
}