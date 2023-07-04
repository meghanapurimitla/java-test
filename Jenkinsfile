pipeline {
  agent any
  parameters {
    string(name: 'PARAMETER_NAME', defaultValue: 'default_value', description: 'Description of the parameter')
  }
  
  stages {
    stage('Read Environment Variables') {
      steps {
        script {
          // Read default Jenkins environment variables
          def jenkinsEnvVars = env
          echo "Jenkins Build Number: ${jenkinsEnvVars.BUILD_NUMBER}"
          echo "Jenkins Job Name: ${jenkinsEnvVars.JOB_NAME}"
          echo "Jenkins Workspace: ${jenkinsEnvVars.WORKSPACE}"
          // Add more environment variables as needed
        }
      }
    }
    
    stage('Build') {
      steps {
        echo "This is the build stage"
      }
    }
    
    stage('Test') {
      steps {
        echo 'Code will be tested here'
      }
    }
    
    stage('SonarQube Analysis') {
      steps {
        // Run SonarQube analysis
        // Replace the placeholder values with actual SonarQube scanner commands or plugin configurations
        // Example: sh 'sonar-scanner -Dsonar.projectKey=my-project -Dsonar.sources=. -Dsonar.host.url=http://sonarqube-server:9000'
        echo 'Running SonarQube analysis'
      }
    }
    
    stage('Publish to Artifactory') {
      steps {
        echo 'Publish to Artifactory'
      }
    }
    
    stage('Deploy to Dev') {
      steps {
        echo 'Deploy to Dev'
      }
    }
    
    stage('Deploy to Test') {
      steps {
        echo 'Deploy to Test'
      }
    }
    
    stage('Deploy to UAT') {
      steps {
        echo 'Deploy to UAT'
      }
    }
    
    stage('Deploy to Stage') {
      steps {
        echo 'Deploy to Stage'
      }
    }
    
    stage('Deploy to Prod') {
      when {
        expression { params.ENVIRNOMENT == 'PROD' }
      steps {
        echo 'Deploy to Prod which is used by customers'
       input(message: 'Are you ready for production?', ok: 'Proceed to production')
      } 
    }
  }
  
  post {
    always {
      // Actions to perform regardless of the pipeline status
      echo 'This post step always executes'
    }
    
    success {
      // Actions to perform only if the pipeline succeeds
      echo 'This post step executes on success'
      emailext (
        subject: "Pipeline Success: ${env.JOB_NAME}",
        body: "The pipeline ${env.JOB_NAME} succeeded.",
        to: "meghanapurimitla@gmail.com"
      )
    }
    
    failure {
      // Actions to perform only if the pipeline fails
      echo 'This post step executes on failure'
      emailext (
        subject: "Pipeline Failure: ${env.JOB_NAME}",
        body: "The pipeline ${env.JOB_NAME} failed. Please check the logs.",
        to: "meghanapurimitla@gmail.com"
      )
    }
    
    unstable {
      // Actions to perform only if the pipeline is marked as unstable
      echo 'This post step executes on unstable'
      emailext (
        subject: "Pipeline Unstable: ${env.JOB_NAME}",
        body: "The pipeline ${env.JOB_NAME} is unstable.",
        to: "meghanapurimitla@gmail.com"
      )
    }
  }
}

}
