pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'bazel build //:ProjectRunner'
      }
    }
  }
}