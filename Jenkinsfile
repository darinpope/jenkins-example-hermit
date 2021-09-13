pipeline {
  agent any

  stages {
    stage('jq') {
      steps {
        sh 'curl https://api.github.com/repos/darinpope/java-web-app/commits?per_page=5 | jq \'.[0]\''
      }
    }
  }
}
