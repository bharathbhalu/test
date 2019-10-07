pipeline {
  agent any
  stages {
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
    stage('SA') {
      steps {
        echo 'Static Analysis Done'
      }
    }
    stage('Unit-Test') {
      steps {
        echo 'Unit Tests are Done'
      }
    }
    stage('PCS') {
      parallel {
        stage('TS Tests') {
          steps {
            echo 'TS'
          }
        }
        stage('Windows Tests') {
          steps {
            echo 'Windows'
          }
        }
        stage('Linux Tests') {
          steps {
            echo 'LINUX'
          }
        }
        stage('Mac Testss') {
          steps {
            echo 'MAC'
          }
        }
        stage('NCM Tests') {
          steps {
            echo 'NCM'
          }
        }
      }
    }
    stage('Image Uploads') {
      parallel {
        stage('Amazon ECR') {
          steps {
            echo 'AMAZON'
          }
        }
        stage('Jfrog') {
          steps {
            echo 'JFROG'
          }
        }
      }
    }
  }
}