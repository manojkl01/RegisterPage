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
        
        nexusArtifactUploader artifacts: [
            [
                artifactId: 'Demo11',
                classifier: '',
                file: '/var/lib/jenkins/jobs/RohitPipeline/config.xml', 
                type: 'war'
            ]
        ], 
            credentialsId: '1b207162-1d0d-4008-a8ee-4c19cbb0887d',
            groupId: 'Demo11', 
            nexusUrl: '65.1.111.57:8081', 
            nexusVersion: 'nexus3',
            protocol: 'http', 
            repository: 'maven-snapshots', 
            version: '1.0-SNAPSHOT'
           }
       }
    }
}
