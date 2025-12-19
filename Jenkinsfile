pipeline {
    agent any
    // environment{
    //     PATH = "/opt/maven/bin/:$PATH"
    //     }
    tools {
        maven ('3.9.11')
    }
    stages {
        stage('rakesh-gitcheckout') {
            steps{
            git branch: 'main', url: 'https://github.com/devopssachin14/jenkins-java2.git'
            }
        }
        stage('rakesh-MavenCheck') {
            steps{
            sh 'mvn --version'
            }
        }
        stage('rakesh-MavenBuild') {
            steps{
            sh 'mvn -B -Dskiptests clean package'
            sh 'mvn validate'
            sh 'mvn install'
            }
        }
        stage('rakesh-Validation') {
            steps{
            sh 'mvn validate'
            }
        }
    }
}
