node {
    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {
        def mvn = tool 'Default Maven';
        withSonarQubeEnv() {
            sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=demo-sonar-qube -Dsonar.login=<sonar_token>"
        }
    }
}