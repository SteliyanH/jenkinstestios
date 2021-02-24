pipeline {
    agent any

    options {
        ansiColor("xterm")
    }
 
    triggers {
        pollSCM ignorePostCommitHooks: true, scmpoll_spec: pollSpec
    }

    stages {

        stage('Reinitialize jenkins keychain') {
            steps {
                sh "fastlane refreshJenkinsKeychain"
            }
        }

        stage('Populate Jenkins Keychain') {
            steps {
                sh "fastlane matchPopulateJenkinsKeychain"
            }
        }

        stage('Build application for beta') {
            steps {
                sh "fastlane buildAppWithGym"
            }
        }
    }
}