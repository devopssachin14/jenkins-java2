pipeline {
    agent any
    // environment{
    //     PATH = "/opt/maven/bin/:$PATH"
    //     }
    tools {
        maven ('3.9.11')
    }
    stages {
        stage('december-gitcheckout') {
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
