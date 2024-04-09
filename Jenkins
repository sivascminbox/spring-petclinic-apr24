pipeline {
    agent { label 'spc' }
        stages {
            stage('git') {
                steps {
                  git url: 'https://github.com/sivascminbox/spring-petclinic-apr24.git', branch: 'main'
                }
            }    
            stage(build) {
                steps {
                  mail bcc: '', body: 'Build is started', cc: '', from: '', replyTo: '', subject: 'Build Started', to: 'all@test.com'
                  sh 'mvn clean package'
                  junit testResults: '**/surefire-reports/*.xml'
                  archive '**/target/SPRING-PETCLINIC*.jar'
                  mail bcc: '', body: 'Build is completed', cc: '', from: '', replyTo: '', subject: 'Build completed', to: 'all@test.com'
                }
            }
        }
}
