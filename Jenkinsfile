pipeline {
    
    agent any
    
    stages{
        stage('git'){
            steps {
                git 'https://github.com/jleetutorial/maven-project.git'
            }
        }
        stage('mvn'){
            steps {
                sh 'mvn package'
            }
        }
        stage('archive'){
            steps {
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
