pipeline {
  agent {label 'slave1'}
    stages {
        stage('Dev') {
            steps {
                sh 'free -g'
            }
        }
    }
    stage('parallel-Build') {
      parallel {
        stage('build-java-11'){
            steps {
                sh 'java --version'
            }
        }
        stage('build-java-8'){
            steps {
              sh 'lsblk'
            }
        }

      } 
    }
  agent{label 'slave2' }
    stage('Test') {
            steps {
                echo "In slave 2 system"
              sh 'hostname'
              sh 'cat /etc/passwd'
            }
        }
     stage('Prod') {
            steps {
               echo "df -h"
            }
        }
    }
  
}
