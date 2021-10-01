pipeline {
    
    agent any
    
    stages{
        stage('copy'){
            steps {
                copyArtifacts filter: '**/*.war', fingerprintArtifacts: true, projectName: 'build-maven', selector: lastSuccessful()
            }
        }
        stage('deploy'){
            steps {
                deploy adapters: [tomcat9(credentialsId: '5bd00886-db3d-4c5a-9cf1-b50f2549efa3', path: '', url: 'http://18.189.27.39:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
