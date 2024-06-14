//
pipeline {
    agent {
      label 'agent01'
    }

    stages {   
        stage("test"){
            steps {
                sh "./mvnw test"                
            }
        }    
        stage("build"){
            steps {
                sh "./mvnw package"                
            }
        }	
        stage ("capture"){
            steps {
                archiveArtifacts artifacts: '**/target/*.jar'
                jacoco()
                junit '**/target/surefire-reports/TEST*.xml'                                
            }
        }
    }
}


