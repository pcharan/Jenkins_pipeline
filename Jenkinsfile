Code_changes = getGitChanges()
pipeline {
    agent any
    parameters{
        choice(name: "Version", choices: ['1.1.20', '1.2.1', '1.3.0'], description:'')
        booleanParam(name: "execute", defaultvalue: true, description:'')
        string(name: "NAME", defaultvalue: "Charan", description:"")
    }
    stages {
      stage("build"){
          when{
              expression {
                  params.execute
              }
          }
        steps {
          echo 'building the application.... '
          echo "Name Parameter value ${params.NAME}"
        }
      }
      stage("test"){
          when{
              expression{
                  params.execute
              }
          }
        steps {
          echo 'Testing the application.... '
        }
      }
      stage("deploy"){
        steps {
          echo 'Deploying the application.... '
            echo "Choices of Version ${params.Version}"
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
