pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Downloading thecode from Github"
                // Get some code from a GitHub repository
                git branch: 'main',
                url: 'https://github.com/vaffen/lspu-demo.git'

            }
        }
    stage('Unit Test') {
        steps {
            echo "Executing Unit test"
        }
    }


    stage('Deploy') {
      steps {
        sh "docker --version"
        sh "docker build -t hello ."
        sh "docker run -itd -p 8085:8080 hello"
        sh "docker ps"
      }
    }
    }
  post { 
    always { 
        cleanWs()
    }
  }
}
