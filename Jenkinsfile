pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage ('Build'){
            steps{
                sh 'mvn clean package'
                 echo "Building phase"
            }
        }
        stage ('Test'){
            steps{
                 echo "Testing phase"
            }
        }
       stage ('Deploy'){
            steps{
                 echo "Deploy phase"
            }
        }
    }
}
