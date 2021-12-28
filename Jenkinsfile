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
    }
    nexusArtifactUploader credentialsId: '', groupId: 'torryharris', nexusUrl: 'http://3.142.77.118:8081/', nexusVersion: 'nexus2', protocol: 'http', repository: 'https://github.com/2sagardeshmukh/RegisterPage.git', version: '1.0'
}
