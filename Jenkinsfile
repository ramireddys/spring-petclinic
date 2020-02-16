pipeline {
     agent any
     stages {
       stage('Pullcode') {
         steps {
	    git  'https://github.com/ramireddys/spring-petclinic.git'

	 }
     }
       stage('Testing') {
          steps {
            sh "mvn  clean test"
            junit 'target/surefire-reports/*.xml'
          }
        }
         
	 stage('Package') {
            steps { 
            sh "mvn package -DskipTests=true"


          }
        }
      }

  


 }



