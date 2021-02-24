pipeline {
    agent any 
    stages {
        stage('Reinitialize jenkins keychain') {
        node('mac') {
            
                steps {
                    sh "./fastlane refreshJenkinsKeychain"
                }
            }
        }
        stage('Populate Jenkins Keychain') {
 node('mac') {
        
            steps {
                sh "./fastlane matchPopulateJenkinsKeychain"
            }
        }
 }
 stage('Build application for beta') {
 node('mac') {
        
            steps {
                sh "./fastlane buildAppWithGym"
            }
        }
    }
    }
}