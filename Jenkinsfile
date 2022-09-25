pipeline{
    agent any
    tools{
        maven 'maven'
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
                deploy adapters: [tomcat7(credentialsId: 'tomcat', path: '', url: 'http://172.31.37.180:8098/')], contextPath: null, war: '**/*.war'
                echo "Deployment.."
            }
        }
    }
}
