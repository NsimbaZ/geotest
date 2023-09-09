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
}// end of stages
}//end of pipeline