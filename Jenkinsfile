ipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('git-clone - Sithabile'){
        steps{
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Team3-etech-engner/roger-slave-demo.git']]])
        }
    }
     stage('parallel-job 1'){
      parallel{
        agent {
    label {
      label 'slave2'
    }
  }
        stage('sub-job1 - Roger'){
          steps{
            sh 'sudo systemctl status jenkins'
            sh 'ps -ef'
          }
        }
          stage('sub-job2 - Kingue'){
           steps{
            sh 'ps -ef'
            sh 'sudo systemctl status jenkins'
          }
        }
      }
    }
    stage('parallel-job 2'){
      parallel{
        agent {
    label {
      label 'slave3'
    }
  }
        stage('sub-job1 - Constance'){
          steps{
            sh 'ps -ef'
            sh 'sudo systemctl status jenkins'
          }
        }
        stage('sub-job2 - Wille'){
          steps{
            sh 'sudo systemctl status jenkins'
            sh 'ps -ef'
          }
        }
      }
    }
  }
}
