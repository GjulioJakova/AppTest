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
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaa'
         bat 'gradlew assembleDebug'
        script {
                    env.FILENAME = sh(returnStdout: true, script: "git tag describe --tags --abbrev=0").trim()
                }
                echo "${env.FILENAME}"
         
      }
    }
  }
}
