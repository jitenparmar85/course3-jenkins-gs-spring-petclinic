pipeline {
    agent any
    stages {
    //def mvnHome
        stage('Preparation') {
            steps {
                git branch: 'main', url: 'https://github.com/jitenparmar85/course3-jenkins-gs-spring-petclinic'
            }
        }
        stage('Build') {
            steps {
                powershell './mvnw package'    
            }
        }
        stage('Results') {
            steps {
                junit '**/target/surefire-reports/TEST-*.xml'
                archiveArtifacts '**/target/*.jar'
                jacoco()
            }
        }
    }
}
