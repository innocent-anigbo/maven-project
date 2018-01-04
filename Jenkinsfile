pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh '/apache-maven-3.5.2/bin/mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
         }
         stage('Deploy to Staging'){
            steps {
                build job: 'deploy tomcat stage'
            }
         }
      }
}
