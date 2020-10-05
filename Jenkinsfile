pipeline {
  agent any
  stages{
    stage('Compile'){
      when {
      tag 'origin/tags/prova-pipeline9'
      }
      steps{
         bat 'echo ciaooo'
      }
    }
  }
}
