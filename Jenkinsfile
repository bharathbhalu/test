pipeline {
  agent any
  stages {
    stage('SA') {
      steps {
        echo 'SA Success'
      }
    }
    stage('CodeCoverage') {
      steps {
        echo 'Code Coverage is Done'
      }
    }
    stage('Builds') {
      parallel {
        stage('TS build') {
          steps {
            echo 'TS build is done'
          }
        }
        stage('BuildClient-Windows') {
          steps {
            echo 'Windows Client Build'
          }
        }
        stage('BuildClient-MAC') {
          steps {
            echo 'Client Mac Build'
          }
        }
        stage('BuildClient-Linux') {
          steps {
            echo 'Client Build For linux'
          }
        }
      }
    }
    stage('PCS') {
      steps {
        echo 'PCS is done'
      }
    }
    stage('Image Uploads') {
      parallel {
        stage('Image Upload-Jfrog') {
          steps {
            echo 'Images Uploaded to Jfrog'
          }
        }
        stage('Image Upload-DockerHub') {
          steps {
            echo 'DockerHub Image Upload Done'
          }
        }
      }
    }
  }
}