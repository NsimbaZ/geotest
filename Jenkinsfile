pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    environment{
        artifact = 'target/bioMedical-0.0.6-SNAPSHOT.jar'
        user_login = 'admin:devops'
        nexus_url = 'http://198.58.119.40:8081/repository/NsimbaZ-repo/'
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
    stage('push to Nexus'){
        steps{
            nexusArtifactUploader artifacts: [[artifactId: 'bioMedical', 
            classifier: '', 
            file: 'target/bioMedical-0.0.6-SNAPSHOT.jar', 
            type: 'jar']], 
            credentialsId: 'ssh-agent-ID', 
            groupId: 'qa', 
            nexusUrl: '198.58.119.40:8081', 
            nexusVersion: 'nexus3', 
            protocol: 'http', 
            repository: 'NsimbaZ-repo', 
            version: '0.0.6-SNAPSHOT'
        }
    }
}// end of stages
}//end of pipeline