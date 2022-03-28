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
                nexusArtifactUploader artifacts: [[artifactId: 'simple-app', classifier: '', file: 'target/simple-app-1.0.0.war', type: 'war']], credentialsId: 'nexus', groupId: 'in.javahome', nexusUrl: '44.203.177.44   ', nexusVersion: 'nexus3', protocol: 'http', repository: 'simple-app-release', version: '1.0.0'
            }
        }
    }
}
