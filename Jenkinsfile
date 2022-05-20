pipeline{
    agent {label 'java11'}
    triggers{
        cron ('H * * * *')
    }
    stages{
        stage ('scm'){
            git 'https://github.com/venkatesh-pogula/jenkins_spring.git'
        }
        stage ('build'){
            sh '''cd /spring-petclinic/Jenkinsfile
                   mvn package'''
        }
        post{
        sucess {
            archive '**/*.jar'
            junit '**/TEST-*.xml'

        }
    }
}