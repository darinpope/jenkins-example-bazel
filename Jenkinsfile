pipeline {
  agent any
  stages {
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