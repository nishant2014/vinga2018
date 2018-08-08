node{
  stage('SCM Checkout'){
    git 'https://github.com/vinga2805/java-maven-sample'
  }
  stage('Compile package'){
    //Defining Maven Home path
    def MVN_HOME = tool name: 'maven-3', type: 'maven'
    sh "${MVN_HOME}/bin/mvn clean package"
    
  stage('SonarQube analysis'){
    def MVN_HOME = tool name: 'maven-3', type: 'maven'
    withSonarQubeEnv('My SonarQube Server') {
    sh "${MVN_HOME}/bin/mvn sonar:sonar"
    }
  }  
  }
  stage('Email Notification'){
    mail bcc: '', body: '''Hello,
    This email is to inform you that the build job has been triggered.

    Thanks and Regards,
    Vishal Ingale''', cc: '', from: '', replyTo: '', subject: 'Jenkins Build Info', to: 'vishalonwork@gmail.com'

  }
  stage('Slack-Notification'){
    slackSend baseUrl: 'https://hooks.slack.com/services/', 
    channel: '#jenkins-demo', 
    color: 'good', 
    message: 'Welcome to Jenkins, Slack!!', 
    teamDomain: 'avika-infotech', 
    tokenCredentialId: 'jenkins-demo'

  }
}
