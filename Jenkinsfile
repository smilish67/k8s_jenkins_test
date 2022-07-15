pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/smilish67/k8s_jenkins_test.git will replace by sed command before RUN
        git url: 'https://github.com/smilish67/k8s_jenkins_test.git', branch: 'main'
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