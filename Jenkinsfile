
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Building...'
                sh 'java -version'
            }
        }
        stage('test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
      success {
          slackSend channel: '#jenkins-build',
                    color: 'good',
                    message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
      }
      failure {
          slackSend channel: '#jenkins-build',
                    color: 'bad',
                    message: "The pipeline ${currentBuild.fullDisplayName} has failed."
      }
    }
}
