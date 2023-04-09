pipeline {

agent any
  
parameters([string(name: 'sub_job', defaultValue: 'True')])
def job1 = Jenkins.instance.getJob('multibranch_two')

stages {
  stage("build") {
      steps {
        if (${sub_job} == 'True') {
          build(job1)
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
