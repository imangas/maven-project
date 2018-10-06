pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                echo 'testing the pipeline' 
                sh 'mvn clean package'
            }
        }
    }
}