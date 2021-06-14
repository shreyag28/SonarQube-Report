pipeline {
    agent master

    tools {
        maven "MAVEN_HOME"
    }

    stages {
        stage('Build') {
            steps {
               
                git 'https://github.com/shreyag28/SonarQube-Report.git'

                
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                
            }

            post {
                
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
