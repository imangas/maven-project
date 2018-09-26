pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        post {
            success {
                echo 'Now Archiving ...'
                archiveArtifacts artifacts: '**/target/*.war'
            }
        }
    }
}