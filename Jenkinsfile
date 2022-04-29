pipeline {
  agent any
  parameters {
    choice(name: 'DEPLOY_TO:', choices: ['Dev', 'ST', 'Prod'], description: 'Choose Enviornment')
  }
  
  stages {
    stage('SettingParm') {
      steps {
        echo "Deploying to: ${params.DEPLOY_TO}"
        input(message: 'Proceed with deploying to ${params.DEPLOY_TO}',, ok: 'Continue')
      }
    }

    stage('Publish') {
      steps {
        writeFile(file: 'outputfile.txt', text: 'testing the write function')
        archiveArtifacts 'outputfile.txt'
      }
    }

    stage('Trigger') {
      steps {
        build 'firstjob'
      }
    }

  }
}
