pipeline {
    agent  {
        label 'master'
    }
  
    stages {
        stage('scm') {
            steps {
                 dir("$WORKSPACE/azure-voting-app-redis") {
                    git branch: "*.*", url: 'https://github.com/einavle/azure-voting-app-redis'
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
