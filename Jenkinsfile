pipeline {
    agent {
      label 'linux'
    }
    
    stages {
      stage('Clone repo role') {
        steps {
            git credentialsId: '9dbad282-a664-4d11-8b60-b273a9a9f248', url: 'git@github.com:prunovr/vector-role.git'
        }
      }
      stage ('Prepare for molecule'){
        steps {
            sh 'pip3 install --user "molecule==3.3.4" "molecule_docker==0.3.3" ansible-lint'
        }
      }
      stage('Run molecule'){
          steps {
            sh 'molecule test'
          }
      }
    }
}