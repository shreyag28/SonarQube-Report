properties([[$class: 'JiraProjectProperty', siteName: 'https://cybagejanshreya.atlassian.net/'], parameters([choice(choices: 'master\nfeature1', description: 'select the branch to build ', name: 'branches')])])
pipeline {
    agent {
    label 'master'
    }

    tools {
        maven "Maven"
    }

    stages {
        stage('$cm Checkout') {
            steps {
               
              echo "Pilling changes from the branch ${params.branches}"
                
            }

            
        }
        stage('SonarQube analysis') {
            steps{
    withSonarQubeEnv('SonarQube ') 
            { 
      bat 'mvn org.sonarsource.scanner.maven:sonar:sonar'
    }
            }
  }
    }
}
