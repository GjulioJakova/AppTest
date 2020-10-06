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
      when { 
           buildingTag() 
      }
      steps{
         bat 'echo %BRANCH_NAME'
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaa'
         bat 'gradlew assembleDebug'
         
      }
    }
  }
}
