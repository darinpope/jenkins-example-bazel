pipeline {
  agent any
  stages {
    stage('verify bazel is installed') {
      steps {
        sh 'bazel version'
      }
    }
    stage('Build the project') {
      steps {
        sh 'bazel build //:ProjectRunner'
      }
    }
    stage('Review the dependency graph') {
      steps {
        sh 'bazel query  --notool_deps --noimplicit_deps "deps(//:ProjectRunner)" --output graph'
      }
    }
  }
}