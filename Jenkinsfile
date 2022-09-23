pipeline{
    agent any
    tools{
        maven 'mvn1'
    }
    stages{
        stage ('Build'){
            steps{
                sh 'mvn clean package'
            }
            post{
                success{
                    echo "Archiving the Artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to tomcat server') {
            steps{
                deploy adapters: [tomcat7(credentialsId: 'tomcatSrv', path: '', url: 'http://13.94.40.245:8089/')], contextPath: null, war: '**/*.war'
                echo "Deployment.."
            }
        }
    }
}
