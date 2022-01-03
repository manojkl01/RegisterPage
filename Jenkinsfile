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
                artifactId: 'Demo1',
                classifier: '',
                file: '/var/lib/jenkins/jobs/PipelineDemo/config.xml', 
                type: 'war'
            ]
        ], 
            credentialsId: '692fe79a-b338-46d0-8bcc-df06878cb8b2',
            groupId: 'Demo1', 
            nexusUrl: '65.0.99.108:8081', 
            nexusVersion: 'nexus3',
            protocol: 'http', 
            repository: 'maven-snapshots', 
            version: '1.0-SNAPSHOT'
           }
       }
    }
}
