pipeline {
   agent any
// test
   stages {
      stage('Git Branching') 
      {
         steps {
            echo "$GIT_BRANCH"
         }
      }
   }
      stage('Docker Build') 
      {
         steps {
            pwsh(script: 'docker images -a ')
            pwsh("""
            cd azure-vote/
            docker images -a 
            docker build -t jenkins-pipeline .
            docker images -a
            cd ..
            """)
         }
            }
      }
  