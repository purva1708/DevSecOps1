pipeline {
  agent any 
  tools {
    maven 'Maven'
    }
   
  stages {
    stage ('Initialize') {
      steps {
        sh '''
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
  
    stage ('Check secrets') {
      steps {
      sh 'trufflehog3 https://github.com/sweetcbk/secirity.git -f json -o truffelhog_output.json || true'
      }
    }
