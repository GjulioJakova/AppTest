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
              env.MY_GIT_TAG = bat(returnStdout: true, script: 'git tag -l --points-at HEAD').trim()
              bat 'echo "${env.BUILD_VERSION}"'
            }
        }
    stage('Compile'){
      when {
      branch 'main'
      }
      steps{
         bat 'echo ciaoooooooooooooooooooooooooooooooooootrgrgtr'
      }
    }
  }
}
