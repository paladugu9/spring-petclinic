pipeline {
    agent any

    stages {
        stage('Cloning Repo') {
            steps {
                 git branch: 'main', url: 'https://github.com/paladugu9/spring-petclinic.git'
                
            }
        }
        stage('Compile Code') {
            steps  {
                sh 'mvn compile -s settings.xml  -Dcheckstyle.skip'
              sh 'id'
            }
        }
        stage('Run Tests & package Code') {
            steps {
               sh 'mvn clean install -s settings.xml  -Dcheckstyle.skip'
              
            }
        }
        stage('Building Docker Image') {
            steps {
                sh 'docker images'
                sh 'docker build -t petclinic:v1 .'
                sh' docker images'
            }
        }
    }
}
