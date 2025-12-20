pipeline {
    agent any
    // environment{
    //     PATH = "/opt/maven/bin/:$PATH"
    //     }
    parameters { 
        choice(name: 'DEPLOY_OR_NOT', choices: ['YES', 'NO'], 
                        description: '')
              }
    tools {
        maven ('3.9.11')
    }
    stages {
        stage('sachin_gitcheckout') {
            when {
                expression {
                    params.DEPLOY_OR_NOT == 'YES'
                }
            }
              steps{
            git branch: 'sachin', url: 'https://github.com/devopssachin14/jenkins-java2.git'
            }
        }
        stage('december-MavenCheck') {
            steps{
               sh 'mvn --version'
            }
        }
        stage('december-MavenBuild') {
            steps{
            sh 'mvn -B -Dskiptests clean package'
            sh 'mvn validate'
            sh 'mvn install'
            }
        }
        stage('december-Validation') {
            steps{
            sh 'mvn validate'
            }
        }
    }
}
