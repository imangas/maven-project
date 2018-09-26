pipeline {
    agent {
        docker {
            reuseNode true
            label 'Maven-3.5'
            image 'maven:3.5.3-jdk-8-alpine'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
            post {
                success {
                    echo 'Now Archiving ...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage('Deploy') {
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}