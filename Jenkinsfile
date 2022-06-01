pipeline {
    agent {
       label 'BUILD_8_JDK'
    }
    triggers {
     cron 'H  */1 * * *'
    }
    stages {
         stage('SourceCode') {
                steps {
                     // One or more steps need to be included within the steps block.
                      git branch: 'declarative', url: 'https://github.com/bvc143/spring-petclinic.git'
                 }
         }
        stage('Build The Code' ){
             steps{
                 sh 'mvn package'
           }
         }
       stage('Archiving and test results'){
           steps{
                junit '**/surefire-reports/*.xml' 
            archiveArtifacts artifacts: '**/*war', followSymlinks: false
           }
         }
    }
}
