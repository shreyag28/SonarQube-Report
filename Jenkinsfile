pipeline {
    agent {
    label 'master'
    }

    tools {
        maven "Maven"
    }

    stages {
        stage('Build') {
            steps {
               
              //  git 'https://github.com/shreyag28/SonarQube-Report.git'

                
                bat "mvn -Dmaven.test.failure.ignore=true clean package"

                
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
