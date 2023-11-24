pipeline{
    agent any
    stages{
        stage('clean')
        {
            steps
            {
                sh 'mvn clean'
            }
        }
        stage('build')
        {
            steps
            {
                sh 'mvn package'
            }
            

        }
        stage("Deploy into tomcat")
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '8f24d946-c251-4ca4-9eeb-a2fc224e1e11', path: '', url: 'http://65.0.135.0:8081/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
