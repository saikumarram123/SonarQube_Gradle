/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    environment{
        def sonar = tool 'SonarScanner'
    }
    stages {
        /* stage('SCM Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/sagarkrp/fakeweb.git'
            //sh 'whoami'
            }
        } */

        stage('SonarQube Analysis') {
            steps {
//                 sh './gradlew sonar \
//                     -Dsonar.projectKey=Gradle_Project \
//                     -Dsonar.projectName='Gradle_Project' \
//                     -Dsonar.host.url=http://localhost:9000 \
//                     -Dsonar.token=sqp_e2497c7ad5f5ed82b3775e082efd2b770f7e6ba7'
                sh 'chmod +x gradlew'
                sh "./gradlew sonar -Dsonar.token=sqp_e2497c7ad5f5ed82b3775e082efd2b770f7e6ba7"
      
           }
        }
    }
}
