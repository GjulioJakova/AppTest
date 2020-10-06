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
                 userRemoteConfigs: scm.userRemoteConfigs
                ])
            }
        }
    stage('Compile'){
    
      steps{
         script {
           def tag  = bat(returnStdout: true, script: "git tag --sort version:refname | tail -1").trim()
                }
                echo "TAG -> ${tag}"
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaadaaaa'
         bat 'gradlew assembleDebug'
       
         
      }
    }
  }
}
