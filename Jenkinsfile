pipeline {
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
  stage ('Test') {
            steps {
                echo 'code will Test here'
            }
        }

        stage ('Sonar Scanning') {
            steps {
                echo 'Sonar Scanning will scan the code here'
            }
        }

        stage('Publish to Artifactory') {
            steps {
                echo 'Publish to Artifactory'
            }
        }

        stage ('Deploy to Dev') {
            steps {
                echo 'Deploy to Dev'
            }
        }

        stage ('Deploy to Test') {
            steps {
                echo 'Deploy to Test'
            }
        }

        stage ('Deploy to UAT') {
            steps {
                echo 'Deploy to UAT'
            }
        }
        stage ('Deploy to Stage') {
            steps {
                echo 'Deploy to Stage'
            }
        }

        stage ('Deploy to prod'){
            steps{
                echo 'Deploy to prod which is used by customers'
            } 
        }
    }
}
