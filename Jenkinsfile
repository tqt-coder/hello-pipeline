pipeline {
  agent any
  stages {
    stage('Clean Up') {
      steps {
        deleteDir()
      }
    }
    stage('Clone Repo') {
      steps {
        sh 'git clone https://github.com/CBoton/spring-boot-hello-world.git'
      }
    }
    stage('Build') {
      steps {
        dir('spring-boot-hello-world') {
          sh 'mvn clean install'
        }
      }
    }
    stage('Test') {
      steps {
        dir('spring-boot-hello-world') {
          sh 'mvn test'
        }
      }
    }
    stage('Package') {
        steps {
          dir('spring-boot-hello-world') {
            sh 'mvn package'
          }
        }
        post {
          success {
            dir('spring-boot-hello-world') {
            archiveArtifacts 'target/*.jar'
            }
          }
        }
    }
    // stage('Copy') {
    //   steps {
    //     fileOperations([fileCopyOperation(
    //     excludes: '',
    //     flattenFiles: false,
    //     includes: '**/*.jar',
    //     targetLocation: "C:\\output"
    //     )])
    //   }
    // }
  }
}

