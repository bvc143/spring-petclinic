node('BUILD_11_JDK'){
      stage('SourceCode'){
          git branch: 'scripted', url: 'https://github.com/bvc143/spring-petclinic.git'
        }
       stage('Build the code'){
        sh 'mvn package'
       }
     stage('Archiving and test results'){
        junit '**/surefire-reports/*.xml' 
          archiveArtifacts artifacts: '**/*war', followSymlinks: false
        }
 


}
