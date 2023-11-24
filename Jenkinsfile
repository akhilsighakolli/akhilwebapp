pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
            post{
                success{
                    echo 'Archiving Artifacts'
                    archiveArtifacts artifacts:'**/target/*.war'
                }
            }

        }
        stage("Deploy into tomcat")
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '0695b3f5-d56d-461e-8a9e-78e8dd2fe294', path: '', url: 'http://3.110.41.46:8082/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
