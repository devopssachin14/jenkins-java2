pipeline {
    agent any
    // environment{
    //     PATH = "/opt/maven/bin/:$PATH"
    //     }
    tools {
        maven ('3.9.11')
    }
    stages {
        stage('umesh-gitcheckout') {
            steps{
            git branch: 'main', url: 'https://github.com/devopssachin14/jenkins-java2.git'
            }
        }
        stage('umesh-MavenCheck') {
            steps{
            sh 'mvn --version'
            }
        }
        stage('umesh-MavenBuild') {
            steps{
            sh 'mvn -B -Dskiptests clean package'
            sh 'mvn validate'
            sh 'mvn install'
            }
        }
        stage('umesh-Validation') {
            steps{
            sh 'mvn validate'
            }
        }
    }
}
