pipeline {
  agent{ label "test" }
  stages {
    stages("build") {
      steps {
        sh """
          docker build -t new_test .
          """
      }
    }
    stage("run") {
      steps {
        sh """
          docker container run --name flask -p 8001:5000 -d new_test
          """
      }
    }
  }
}
