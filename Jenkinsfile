properties([pipelineTriggers([githubPush()])])

pipeline {
  agent any
  stages{
    stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: scm.branches,
                 doGenerateSubmoduleConfigurations: scm.doGenerateSubmoduleConfigurations,
                 extensions: [[$class: 'CloneOption', noTags: false, shallow: false, depth: 0, reference: '']],
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
                    env.TAG_NAME  = bat(returnStdout: true, script: "git tag --contains").trim()
                }
                echo "TAG -> ${env.TAG_NAME}"
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaaa'
         bat 'gradlew assembleDebug'
       
         
      }
    }
  }
}
