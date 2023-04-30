/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    environment{
        SONAR_LOGIN = credentials('Sonar_Scan_Token')
    }
    stages {
        /* stage('SCM Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/sagarkrp/fakeweb.git'
            //sh 'whoami'
            }
        } */
        
        stage('Gradle Build') {
            steps {
                sh 'chmod +x gradlew'
                sh "./gradlew build"
            }
        }

        stage('SonarQube Analysis') {
            steps {
                sh 'chmod +x gradlew'
                sh "./gradlew sonar -Dsonar.token=$SONAR_LOGIN"
      
           }
        }
        
        stage('Qualty Gate') {
            steps {
                timeout(time 10, unit: 'MINUTES')
                {
                    waitForQualtyGate abortPipeline: true
                }
           }
        }
    }
}
