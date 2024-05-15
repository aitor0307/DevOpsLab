pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        //Stage 2.1 : publish to Nexus
        stage ('Publish to Nexus') {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.1.2.war', type: 'war']], credentialsId: 'a77b7387-dad1-4831-81cc-92d1df9d5065', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.229:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'AitorsDevOpsLab-SNAPSHOT', version: '0.2.0'
            }
        }

        // Stage3 : Publish the source code to Sonarqube
        stage ('Sonarqube Analysis'){
            steps {
                echo ' deploying... '

            }
        }

        
        
    }

}
