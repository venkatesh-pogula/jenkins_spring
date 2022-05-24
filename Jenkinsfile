pipeline {
    agent {label 'node_java_11'}
    triggers{
        cron ('H * * * *')
    }

     stages{
        stage ('scm'){
            steps{
            git branch: 'declarative' url: 'https://github.com/venkatesh-pogula/jenkins_spring.git'
            }
        }
          stage ('build'){
              steps{
              sh 'mvn clean package'
              }       
        }
     }    
          post{
          sucess{
              archive '**/*.jar'
              junit '**/TEST-*.xml'

            }
       } 
}       