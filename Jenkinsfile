pipeline {
    agent any

    stages {
        stage('clone git repo') {
            steps {
                git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                sh "/opt/apache-maven-3.9.8/bin/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=afari-darko_FULL-CICD-Project_2478423f-ebb4-46bb-a02d-13bbf373cbc3 -Dsonar.projectName='FULL-CICD-Project'"
            }
        }
        stage('package the app') {
            steps {
                sh '/opt/apache-maven-3.9.8/bin/mvn clean package'
            }
        }
    }
}
