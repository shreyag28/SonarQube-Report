//properties([[$class: 'JiraProjectProperty', siteName: 'https://cybagejanshreya.atlassian.net/'], parameters([choice(choices: 'master\nfeature1', description: 'select the branch to build ', name: 'branches')])])
pipeline {
    agent {
    label 'master'
    }

    tools {
        maven "Maven"
    }
    parameters {
       string(defaultValue: 'DefaultJob', description: 'Name of the Job', name: 'Job', trim: false)
    
  }

    stages {
        stage('$cm Checkout') {
            steps {
               
              echo "Pilling changes from the branch ${params.Job}"
                
            }

            
        }
        stage('SonarQube analysis') {
            steps{
    withSonarQubeEnv('SonarQube ') 
            { 
      bat 'sonar-scanner'
    }
            }
  }
    }
}
