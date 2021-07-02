//properties([[$class: 'JiraProjectProperty', siteName: 'https://cybagejanshreya.atlassian.net/'], parameters([choice(choices: 'master\nfeature1', description: 'select the branch to build ', name: 'branches')])])
pipeline {
    agent {
    label 'Agent1'
    }

    tools {
        maven "Maven"
    }
    parameters {
       string(defaultValue: 'DefaultJob', description: 'Name of the Job', name: 'Job', trim: false)
        booleanParam(defaultValue: true, description: 'select the value', name: 'Toggle')
        choice(choices: ['Master', 'Feature1'], description: 'Select the branch', name: 'Branch')
        text(defaultValue: 'Jenkins job', description: 'Write about the Job', name: 'Description')
    
  }

    stages {
        stage('Welcome Stage ') {
            steps {
               
                echo "Name of the following Job ${params.Job}" 
                echo "Value selected is ${params.Toggle}"
              echo "Pilling changes from the branch ${params.Branch}"
                echo "Details of the Job ${params.Description}"
                
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
