pipeline {
    agent any
    stages {
        stage('source code') {
            steps {
                git url: 'https://github.com/Anil95123/spring-petclinic.git', branch: 'decl'
            }
        }
        stage('build') {
            steps {
                agent {label 'openjdk-11-maven1'}
                sh 'mvn package' 
                    
            }
        }
    stage('Archive the Artificats') {
        steps {
            archive 'target/*.jar'
      }
    }
    stage('Junit Results') {
       steps {
            junit "**/surefire-reports/*.xml"
           }
      }
    }
}