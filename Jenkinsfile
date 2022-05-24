pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    
    stages{
        stage('Build'){
            steps{
                 sh script: 'mvn clean package'
            }
        }
        stage('Upload War To Nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'simple-app', classifier: '', file: 'target/sample-3.0.0-SNAPSHOT.war', type: '']], credentialsId: 'Git', groupId: 'in.javahome', nexusUrl: 'http://3.109.59.79:8081/#admin/repository', nexusVersion: 'nexus3', protocol: 'http', repository: 'http://3.109.59.79:8081/repository/latest_spring3/', version: '3.0.0-SNAPSHOT'
            }
        }
    }
}
