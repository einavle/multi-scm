pipeline {
    agent  {
        label 'master'
    }
  
    stages {
        stage('scm') {
            steps {
                 dir("$WORKSPACE/azure-voting-app-redis") {
                     echo "git branch is ${env.GIT_BRANCH}"
                    
                     git branch: '**', url:  'https://github.com/einavle/azure-voting-app-redis'
                     echo "triggered git branch is ${env.BRANCH_NAME}"
                     echo "going to print the envs"
                     sh 'printenv'
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
