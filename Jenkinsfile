pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M2" and add it to the path.
        maven "M2_HOME"
    }
    
    stages {
        stage('GIT') {
            steps {
                git pull
                echo "Getting Project from Git";
                
                  }
            }
            
        stage('MVN CLEAN'){  
            steps {
                sh 'mvn clean'
                  }
        }        
        stage('MVN COMPILE'){
            steps {
                sh 'mvn compile'
                  }
        }          
        stage('MVN SONARQUBE'){
            steps{
                sh 'mvn admin:sonar \
  -Dsonar.projectKey=JenkinsAchatProject \
  -Dsonar.host.url=http://172.20.10.10:9000 \
  -Dsonar.login=b0f501313933656aed1e036e78366489cd7af0e9'
                 }
        }    
   }
}