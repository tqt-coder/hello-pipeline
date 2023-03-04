pipeline {
  agent
  {
    docker { image 'maven:3.9.0-eclipse-temurin-11'
    }
  }
  stages {
    stage('Clean Up') {
      steps {
        deleteDir()
      }
    }
    stage('Clone Repo') {
      steps {
        sh 'git clone https://github.com/tranquoctuan2001/hello-pipeline.git'
      }
    }
    stage('Build') {
      steps {
          sh 'cd ./hello-pipeline'
          sh 'mvn clean install'
      }
    }

    // stage('Test') {
    //   steps {
    //     dir('spring-boot-hello-world') {
    //       sh 'mvn test'
    //     }
    //   }
    // }
    // stage('Package') {
    //     steps {
    //       dir('spring-boot-hello-world') {
    //         sh 'mvn package'
    //       }
    //     }
    //     post {
    //       success {
    //         dir('spring-boot-hello-world') {
    //         archiveArtifacts 'target/*.jar'
    //         }
    //       }
    //     }
    // }
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

