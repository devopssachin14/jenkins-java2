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
            git branch: 'sachin', url: 'https://github.com/devopssachin14/jenkins-java2.git'
            }
        }
        stage('sachin-MavenCheck') {
            steps{
            sh 'mvn --version'
            }
        }
        stage('sachin-MavenBuild') {
            steps{
            sh 'mvn -B -Dskiptests clean package'
            sh 'mvn validate'
            sh 'mvn install'
            }
        }
        stage('sachin-Validation') {
            steps{
            sh 'mvn validate'
            }
        }
    }
}
