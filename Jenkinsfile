pipeline {
    agent any

    stages {
        stage('clone git repo') {
            steps {
                git 'https://github.com/afari-darko/test-maven-app.git'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                sh "/home/ec2-user/sonar-scanner/bin/sonar-scanner -Dsonar.projectKey=afari-darko_test-maven-app_cf1dc896-6a81-4d46-8670-5446ca3ede64 -Dsonar.sources=. -Dsonar.host.url=http://18.175.115.66:9000 -Dsonar.token=sqp_08fbe69abaef9082611f2d85e28722f0298f611e"
                //sh "/opt/apache-maven-3.9.8/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=afari-darko_test-maven-app_cf1dc896-6a81-4d46-8670-5446ca3ede64 -Dsonar.projectName='test-maven-app'"
            }
        }
        stage('package the app') {
            steps {
                sh '/opt/apache-maven-3.9.8/bin/mvn clean package'
            }
        }
    }
}
