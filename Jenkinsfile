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
         script {
                    env.FILENAME = bat(returnStdout: true, script: "git tag --contains").trim()
                }
                echo "${env.FILENAME}"
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaa'
         bat 'gradlew assembleDebug'
       
         
      }
    }
  }
}
