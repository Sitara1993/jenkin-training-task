pipeline {
  agent any
  stages {
    stage ("Checkout"){
      steps{
        echo 'Pulling the code from the dev branch'
      }
    }
    stage ("Build"){
      steps{
        echo 'Building the application'
      }
    }
    stage ("Test"){
      steps{
        echo 'Testing the application'
      }   
    }
stage ("Deploy"){
      steps{
        echo 'Deploing the application'
      } 
  post {
        success {
            emailext (
                to: 'recipient@example.com',
                subject: "Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The build was successful!\n\n" +
                      "Job: ${env.JOB_NAME}\n" +
                      "Build Number: ${env.BUILD_NUMBER}\n" +
                      "Build URL: ${env.BUILD_URL}\n" +
                      "Built by: ${env.BUILD_USER}\n"
            )
        }
        failure {
            emailext (
                to: 'recipient@example.com',
                subject: "Build Failure: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The build failed.\n\n" +
                      "Job: ${env.JOB_NAME}\n" +
                      "Build Number: ${env.BUILD_NUMBER}\n" +
                      "Build URL: ${env.BUILD_URL}\n" +
                      "Built by: ${env.BUILD_USER}\n" +
                      "Please check the Jenkins job for details."
            )
        }
  }
}
}
}
