pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    stages{
    stage('maven clean'){
        steps{
            sh 'mvn clean'
        }
    }
    stage('maven install'){
        steps{
            sh 'mvn install'
        }
    }
    stage('maven package'){
        steps{
            sh 'mvn package'
        }
    }
    stage('upload to nexus'){
        steps{
            sh 'nexusArtifactUploader artifacts: [[artifactId: 'bioMedical', classifier: '', file: 'target/bioMedical-0.0.2-SNAPSHOT.jar', type: '']],
             credentialsId: 'NexusID',
              groupId: 'qa',
               nexusUrl: '198.58.119.40:8081/',
                nexusVersion: 'nexus3',
                 protocol: 'http',
                  repository: 'NsimbaZ-repo',
                   version: '0.0.2''
        }
    }
    }
}