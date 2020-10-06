properties([pipelineTriggers([githubPush()])])

pipeline {
  agent any
  stages{
    stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'main']],
                 userRemoteConfigs: [[
                    url: 'https://github.com/GjulioJakova/AppTest.git',
                    credentialsId: '',
                 ]]
                ])
            }
        }
    stage('Compile'){
      steps{
         when { 
           buildingTag() 
         }
         bat 'echo %BRANCH_NAME'
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaa'
         bat 'gradlew assembleDebug'
         
      }
    }
  }
}
