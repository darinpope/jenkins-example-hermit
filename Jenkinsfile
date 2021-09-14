pipeline {
  agent any
  environment {
    HERMIT_ENV_VARS = sh(returnStdout: true, script: './bin/hermit env --raw').trim()
  }
  stages {
    stage('jq') {
      steps {
        withEnv(HERMIT_ENV_VARS.split('\n').toList()) {
          sh 'curl https://api.github.com/repos/darinpope/java-web-app/commits?per_page=5 | jq \'.[0]\''
        }
      }
    }
  }
}
