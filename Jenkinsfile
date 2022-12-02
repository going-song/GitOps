pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // git@github.com:going-song/GitOps.git will replace by sed command before RUN
        //git url: 'git@github.com:going-song/GitOps.git', branch: 'main'
        git url: 'https://github.com/going-song/GitOps.git', branch: 'main'
          
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}
