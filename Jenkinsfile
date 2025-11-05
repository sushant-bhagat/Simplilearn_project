Create a pipeline Job and run it to get notifications on Slack
pipeline{   
    agent any  
    tools{
        maven 'mymaven'
    }
    stages{   
        stage('slackNotiifaction')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
                sh 'mvn test'
            }
            post{
                success{
                    slackSend channel: 'jenkins-demo', message: 'Pipeline job executed successfully'
                }
                failure{
                    slackSend channel: 'jenkins-demo', message: 'Pipeline job Failed..'
                }
            }
        }
    }
}
