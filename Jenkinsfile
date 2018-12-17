pipeline {
    options {
      disableConcurrentBuilds()
    }
    agent {
      label "jenkins-maven"
    }
    stages {
        stage('Validate Environment') {
            steps {
                echo 'Building..'
                sh 'jx step helm build -d charts/akasha-k8-php'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            when {
              branch 'master'
            }
            steps {
                echo 'Deploying....'
                container('maven') {
                  dir('env') {
                    sh 'jx step helm apply -d charts/akasha-k8-php'
                  }
                }
            }
        }
    }
}
