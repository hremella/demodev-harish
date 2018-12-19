pipeline {
    agent {label 'jenkins_dev_dcos' }
     environment {
        GIT_SHA_SHORT="${GIT_COMMIT[0..6]}"
    }

    stages {
      stage('Checking out democomm-harish') {
        steps {
            sh 'mkdir -p democomm-harish'
            dir('devcomm-harish'){
               sh:"""https://github.com/hremella/democomm-harish/tree/democomm-harish"""
            }
            dir('democomm-harish'){
               echo "Building democomm-harish"
               sh 'mvn clean install'
            }
        }
      }
      stage('Checking out demotest-harish') {
        steps {
            sh 'mkdir -p demotest-harish'
            dir('demotest-harish'){
               sh """https://github.com/hremella/demotest-harish/tree/demotest-harish"""
            }
            dir('devtest-harish'){
               echo "demotest-harish"
               sh 'mvn clean install'
            }
        }
      }
      stage('BUILD') {
        steps {
          echo "Git commit sha is ${GIT_SHA_SHORT}"
          echo "building the code"
        }
    stage('INTEGERATION TEST') {
        steps {
            sh 'echo "run integeration tests here"'
        }
      }
      stage('DOCKER BUILD') {
        steps { 
            
       echo "building the docker"
          }
        }
      }
   
      '''
    }
 }
     stage ('marathon deploy') {
      steps {
     echo  'marathon deploy'
         }
      }
    }


