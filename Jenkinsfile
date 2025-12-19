pipeline {
    agent any
    // environment{
    //     PATH = "/opt/maven/bin/:$PATH"
    //     }
    tools {
        maven ('3.9.11')
    }
    stages {
        stage('gitcheckout') {
            steps{
            git branch: 'main', url: 'https://github.com/devopssachin14/jenkins-java2.git'
            }
        }
        stage('MavenCheck') {
            steps{
            sh 'mvn --version'
            }
        }
        stage('MavenBuild') {
            steps{
            sh 'mvn -B -Dskiptests clean package'
            sh 'mvn validate'
            sh 'mvn install'
            }
        }
        stage('Validation') {
            steps{
            sh 'mvn validate'
            }
        }
    }
}
