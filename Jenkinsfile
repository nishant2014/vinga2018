node{
  stage('SCM Checkout'){
    git 'https://github.com/vinga2805/java-maven-sample'
  }
  stage('Compile package'){
    //Defining Maven Home path
    def MVN_HOME = tool name: 'maven-3', type: 'maven'
    sh "${MVN_HOME}/bin/mvn clean package"
  }
  stage('Email Notification'){
    mail bcc: '', body: '''Hello,
    This email is to inform you that the build job has been triggered.

    Thanks and Regards,
    Vishal Ingale''', cc: '', from: '', replyTo: '', subject: 'Jenkins Build Info', to: 'vishalonwork@gmail.com'

  }
}
