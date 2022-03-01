pipeline {
  agent any
  tools {
    maven 'mymaven'
    jdk 'myjdk'
  }
  stages {
    stage ('Clone git') {
      steps {
        git 'https://github.com/doct15/example-tomcat-war.git'
      }
    }
    
    stage ('Build war file') {
      steps {
        sh 'mvn clean install'
      }
    }
    
    /*stage ('SSH to Tomcat') {
      steps {
        sshagent(['tomcat']) {
          sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war jenkins@172.31.33.36:/var/lib/tomcat9/webapps'
        }
      }
    }*/
  }
}
