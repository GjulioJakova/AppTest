node {
  withCredentials([usernamePassword(credentialsId: 'mycreds', usernameVariable: 'gjuliojakova@yahoo.com', passwordVariable: 'prince.27')]) {
  sh 'cf login some.awesome.url -u $USERNAME -p $PASSWORD'

}
 stage('SCM Checkout'){
    git 'https://github.com/GjulioJakova/AppTest.git'
  }
  stage('Compile'){
    when {
     tag 'prova-pipeline2'
    }
    sh 'echo ciaooo'
  }
}
