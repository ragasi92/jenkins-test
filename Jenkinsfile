pipeline {
  agent any
  tools {
    nodejs 'node-11.0.0'
  }

  options {
    timeout(time: 2, unit: 'MINUTES')
  }


    stage('Run tests') {
      steps {
        sh 'npm t'
      }
    }
    stage('Run parametized'){
        steps{
            build job: 'parameterized', parameters: [string(name: 'ROOT_ID', value: '$BUILD_NUMBER')]
          
        }
    }
  }
}
