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
                    env.TAGNAME  = bat(returnStdout: true, script: "git tag --contains").trim()
                }
                echo "TAG -> ${env.TAGNAME}"
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaaa'
         bat 'gradlew assembleDebug'
       
         
      }
    }
  }
}
