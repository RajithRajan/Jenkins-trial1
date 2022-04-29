pipeline {
  agent any
  stages {
    stage('SettingParm') {
      steps {
        echo "Deploying to: ${params.DEPLOY_TO}"
        input(message: 'Proceed with deploying to ${params.DEPLOY_TO}', ok: 'Continue')
      }
    }

    stage('Publish') {
      parallel {
        stage('Publish') {
          steps {
            writeFile(file: 'outputfile.txt', text: 'testing the write function')
            archiveArtifacts 'outputfile.txt'
          }
        }

        stage('Parallel') {
          steps {
            echo 'Parallel task'
          }
        }

      }
    }

    stage('Trigger') {
      steps {
        build 'JobTrigger/Deploy', parameters [string(name: 'DEPLOY_TO', value: "${params.DEPLOY_TO}")]
      }
    }

  }
  parameters {
    choice(name: 'DEPLOY_TO', choices: ['Dev', 'ST', 'Prod'], description: 'Choose Enviornment')
  }
}
