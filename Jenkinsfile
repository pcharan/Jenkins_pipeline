Code_changes = getGitChanges()
pipeline {
    agent any
    stages {
      stage("build"){
          when{
              expression {
                  BRANCH_NAME = 'main' && Code_changes == true
              }
          }
        steps {
          echo 'building the application.... '
        }
      }
      stage("test"){
          when{
              expression{
                  BRANCH_NAME = 'main'
              }
          }
        steps {
          echo 'Testing the application.... '
        }
      }
      stage("deploy"){
        steps {
          echo 'Deploying the application.... '
        }
      }
    }
    post{
        always{
            echo 'Completed all Tasks...'
        }
        success{
            echo ' all Tasks are successful ...'
        }
        failure{
            echo 'Failed...'
        } 
    }
}
