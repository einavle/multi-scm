pipeline {
    agent  {
        label 'master'
    }
    parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
    stages {
        stage('scm') {
            steps {
                 dir("$WORKSPACE/azure-voting-app-redis") {
                    git branch: "${params.BRANCH}", url: 'https://github.com/einavle/azure-voting-app-redis'
                 }
            }
        }
        stage('scm 2') {
          steps {
              dir("$WORKSPACE/earnix-task") {
                git branch: 'master', url: 'https://github.com/einavle/earnix-task'
              }
            }
        }
    }
}
