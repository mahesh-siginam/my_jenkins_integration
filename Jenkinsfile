pipeline {

agent any
stages {
  stage("build") {
      steps {
        echo "build stage"
      }
  }
  stage("test") {
      steps {
        echo "change to test stage"
      }
  }
  stage("deploy") {
      steps {
        echo "deploy stage"
      }
  }
   stage("Email Notification") {
      steps {
        mail body:'''HI this is a test mail from my multi branch pipeline''',
          to: 'siginammahesh5@gmail.com', subject: '''Jenkins Test Email Notification'''
      }
  }
}

}
