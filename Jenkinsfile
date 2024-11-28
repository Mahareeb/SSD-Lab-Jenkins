pipeline {
    agent any
    stages 
    {
        stage('Build') {
          steps {
          echo 'Building..'
          // Here you can define commands for your build
        }
      }
    stage('Test') 
    {
      steps {
      echo 'Testing..'
      // Here you can define commands for your tests
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
        // Here you can define commands for your deployment
        }
      }
     post{
        //The conditions here will execute after the build is done
    }
    always{
         //The conditions here will execute regardless of the result of the build
        echo 'Post Build Running....'
    }
    failure{
         //The conditions here will execute if the build has failed
        echo 'Post action if the build fails....'
    }
  }
   
}
