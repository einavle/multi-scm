pipeline {
    agent  {
        label 'master'
    }
  
    stages {
        stage('scm') {
            steps {
                 dir("$WORKSPACE/azure-voting-app-redis") {
                     echo "git branch is ${env.GIT_BRANCH}"
                     script{
                         for(e in env){
                             echo e + " is " + ${e}
                            }
                     }
                    
                     git branch: '**', url:  'https://github.com/einavle/azure-voting-app-redis'
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
