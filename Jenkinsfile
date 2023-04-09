pipeline {

agent any
  
  parameters{
    string(name: 'sub_job', defaultValue: 'True')
  }

stages {
  stage("build") {
    when {
      expression {params.sub_job == 'True'}
    }
    steps {
      script {
        def result = build job: 'multibranch_two', propagate: false, wait: false
      }
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
