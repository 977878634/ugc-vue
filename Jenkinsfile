pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('pull') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        bat(encoding: 'UTF_8', returnStdout: true, script: ' git pull https://github.com/just-dj/ugc-vue.git', returnStatus: true)
      }
    }
    stage('build') {
      steps {
        bat(script: 'docker build  -t test/test:lates .', encoding: 'UTF-8', returnStatus: true, returnStdout: true)
      }
    }
  }
}