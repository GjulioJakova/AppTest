pipeline {
  agent any
  stages{
    stage('Compile'){
      when {
      tag 'origin/tags/prova-pipeline10'
      }
      steps{
         bat 'echo ciaooo'
      }
    }
  }
}
