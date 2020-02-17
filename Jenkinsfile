pipeline {
     agent any
     tools {
          maven 'maven1'
	   }
     stages {
       stage('Pullcode') {
         steps {
	    git  'https://github.com/ramireddys/spring-petclinic.git'

	 }
     }
       
         
	 stage('Package') {
            steps { 
            sh "mvn clean package"


          }
        }
      }

  


 }



