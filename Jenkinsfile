pipeline {
    options {
      disableConcurrentBuilds()
    }
    agent {
      label "jenkins-maven"
    }
    environment {
      DEPLOY_NAMESPACE = "jx-staging"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
