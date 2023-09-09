pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    environment{
        artifact = 'target/bioMedical-0.0.5-SNAPSHOT.jar'
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
            sh 'curl --upload-file ${artifact} -u ${user_login} -v ${nexus_url}'
        }
    }
}// end of stages
}//end of pipeline