pipeline {
   agent any
   stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/prakan2/JenkinsCI.git'
        echo "entered into the spring"  
       }
    }
    stage("get inside the folder") {
      steps {
        sh "ls -la"
        echo "entered the workspace"
        sh "chmod 755 gradlew"
        sh "chmod 755 mvnw"
        echo " permissions given to maven and gradle"
      }
    }
    stage("maven clean") {
      steps {
        sh "./mvnw clean"
        echo "maven clean complete"
      }
    }
    stage("maven build") {
      steps {
        sh "./mvnw install"
        echo "maven install complete"
      }
    }
    stage("maven package") {
      steps {
        sh "./mvnw package"
        echo "maven packaging complete"
      }
    }
    stage("running the jar file") {
      steps {
        echo "running the packaged jar file"
      }
    }
    stage("Building docker image") {
      steps {
        sh "docker build -t jenkinsci ."
        echo "docker image generated"
      }
    }
  }
}
