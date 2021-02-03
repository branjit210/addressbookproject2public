pipeline {
    tools
    {
        jdk 'myjdk'
        maven 'mymaven'
    }
    agent any
    stages {
        stage ('checkout') {
            steps {
                git 'https://github.com/branjit210/addressbookproject2public.git'
            }
        }
        stage ('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage ('codereview') {
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        stage ('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage ('metriccheck') {
            steps {
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }
        stage ('package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
