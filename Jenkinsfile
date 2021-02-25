pipeline {
    agent any 
    stages {

        stage('Checkout code') {
            steps {
                node('Mac') {
                    checkout scm
                }
            }
        }
        stage('Reinitialize jenkins keychain') {
            steps {
                node('Mac') {
                    sh "fastlane refreshJenkinsKeychain"
                }
            }
        }
        stage('Populate Jenkins Keychain') {
            steps {
                node('Mac') {
                    sh "fastlane matchPopulateJenkinsKeychain"
                }
            }
        }

        stage('Build application for beta') {       
            steps {
                node('Mac') {
                    sh "fastlane buildAppWithGym"
                }
            }
        }
    }
}