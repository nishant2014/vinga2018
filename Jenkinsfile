node{
  stage('SCM Checkout'){
    git 'https://github.com/vinga2805/java-maven-sample'
  }
  stage('Compile package'){
  sh 'mvn clean package'
  }
}
