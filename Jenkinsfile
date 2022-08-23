pipeline {
    agent any
    options { buildDiscarder(logRotator(numToKeepStr: '2')) }
    stages {
        stage('Hello') {
            steps {
              checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkins-git -cred', url: 'https://github.com/sathish441/maven-git.git']]])
            }
        }
        stage('build') {
            steps{
                script{
                    sh 'mvn clean package'
                }
            }
        }
    }
}
