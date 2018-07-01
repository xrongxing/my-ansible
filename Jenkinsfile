pipeline {
  agent {
    node {
      label 'slave-0'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git 'git@github.com:xrongxing/my-ansible.git'
      }
    }
    stage('build script') {
      steps {
        sh '''for files in `find . -type f -name "*.yml"`
    do
        ansible-lint $files
    done'''
      }
    }
    stage('display') {
      steps {
        sh 'echo "ok,wait ssh copy"'
      }
    }
  }
}