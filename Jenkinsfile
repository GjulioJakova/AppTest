node {
  stage('SCM Checkout'){
    git 'https://github.com/GjulioJakova/AppTest.git'
  }
  stage('Compile'){
    when {
     tag 'prova'
    }
    sh 'echo ciaooo'
  }
}
