properties([pipelineTriggers([githubPush()])])

pipeline {
  agent any
  environment {
        GNU_HOME = 'C:\Users\admin\Downloads\UnxUtils.zip\bin'
    }
  stages{
    stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: scm.branches,
                 doGenerateSubmoduleConfigurations: scm.doGenerateSubmoduleConfigurations,
                 extensions: [[$class: 'CloneOption', noTags: false, shallow: false, depth: 0, reference: '']],
                 userRemoteConfigs: scm.userRemoteConfigs
                ])
            }
        }
    stage('Compile'){
    
      steps{
         script {
           def tag  = bat(returnStdout: true, script: "git tag --sort version:refname | ${GNU_HOME}/sh/tail -1").trim()
                }
                echo "TAG -> ${tag}"
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaaaaa'
         bat 'gradlew assembleDebug'
       
         
      }
    }
  }
}
