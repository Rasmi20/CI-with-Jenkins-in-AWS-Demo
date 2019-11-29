#!/usr/bin/env groovy
node('Node02'){
  stage('checkout scm'){
     checkout scm
     
 }
  stage('build & Package') {
     //def mvnHome
     //mvnHome = tool 'M3'
     sh ''' 
        source /etc/profile.d/maven.sh
        

        cd /var/lib/jenkins/workspace/try_jenkinsfile;

        mvn clean install
      '''
   }
  
  stage('Static Code Analysis'){
       sh '''
       source /etc/profile.d/maven.sh
       cd /var/lib/jenkins/workspace/try_jenkinsfile;
       mvn clean verify sonar:sonar
       '''
   }
}
