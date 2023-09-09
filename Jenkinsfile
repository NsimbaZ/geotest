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
            sh 'curl --upload-file my.zip -u admin:admin123 -v http://localhost:8081/nexus/service/local/repositories/releases/content-compressed/foo/bar'
        }
    }
}// end of stages
}//end of pipeline