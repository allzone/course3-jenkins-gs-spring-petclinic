//
pipeline {
    agent {
      label 'agent01'
    }

    stages {
        stage("checkout") {
            steps {
                sh "ls"
                git branch:'main', url: 'https://github.com/g0t4/course3-jenkins-gs-spring-petclinic'
                sh "ls"
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


