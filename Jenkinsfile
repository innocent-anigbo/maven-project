pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh '/apache-maven-3.5.2/mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
