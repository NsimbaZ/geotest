# patients_geolocation
Project to locate patients in order to facilitate their home appointments by medical specialists
test #2

    stage('upload to nexus'){
        steps{
            sh 'nexusArtifactUploader artifacts: [[artifactId: 'bioMedical',
             classifier: '', 
             file: 'target/bioMedical-0.0.2-SNAPSHOT.jar',
             type: '']],
             credentialsId: 'NexusID',
              groupId: 'qa',
               nexusUrl: ${nexus_url},
                nexusVersion: 'nexus3',
                 protocol: 'http',
                  repository: 'NsimbaZ-repo',
                   version: '0.0.2''
        }
    }