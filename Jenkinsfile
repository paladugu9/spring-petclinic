pipeline {
    agent any

    stages {
        stage('Cloning REpo') {
            steps {
                 git branch: 'main', url: 'https://github.com/paladugu9/spring-petclinic.git'
                
            }
        }
        stage('Compile Code') {
            steps  {
              //  sh 'mvn compile -s settings.xml  -Dcheckstyle.skip'
              sh 'id'
            }
        }
        stage('Run Tests & package Code') {
            steps {
               sh 'mvn clean install -s settings.xml  -Dcheckstyle.skip'
              
            }
        }
        stage('Building Docker-Image And Running Image ') {
            steps {
                sh 'docker images'
                sh 'docker build -t petclinic:v1 .'
              
                //below are run command
                // sh 'docker run -itd -p 8081:8081 petclinic:v1'
            }
        }
    }
}
