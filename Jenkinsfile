pipeline{
  agent any
  environment{
  NEW_VERSION="1.2.0"
    git_credentails=credentials('	githud_cred')
  }
   stages{
  
    stage('init'){
      steps{
        echo 'this is init stage' 
    }
  }
   
    stage('compile'){
        steps{
          echo 'this is compile stage'
          echo "build version ${NEW_VERSION}"
      }
     }
    
     stage('build'){
        steps{
          echo 'this is build stage'
      }
     }
    
   stage('test'){
     when{
       expression{
       BRANCH_NAME='development'
       }
     }
      steps{
        echo 'this is test stage'
      }
     }
    
     stage('deploy'){
      steps{
       echo 'this is deploy stage'
        echo " need credentials ${git_credentails}"
      }
     }
   }
  post{
    always{
    echo "post build always condition"
    }
    success{
    echo" all build s are success"
    }
  }
}
