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
                    def tag  = bat(script: 'git describe --tags $(git rev-list --tags --max-count=1)', returnStdout: true).trim()
                }
                echo "TAG -> ${tag}"
         bat 'echo evvaaaaaaaaaaaaaaaaaaaaaaai era oraaaaaa'
         bat 'gradlew assembleDebug'
       
         
      }
    }
  }
}
