pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    environment{
        nexus_url = '198.58.119.40:8081'
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
    stage(){
        steps{
            sh 'curl --upload-file target/bioMedical-0.0.3-SNAPSHOT.jar -u admin:devops -v http://198.58.119.40:8081/repository/NsimbaZ-repo/'
        }
    }
}// end of stages
}//end of pipeline