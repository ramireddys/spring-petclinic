pipeline {
     agent any
     stages {
       stage('Pullcode') {
         steps {
	    git  'https://github.com/ramireddys/spring-petclinic.git'

	 }
     }
       
         
	 stage('Package') {
            steps { 
            sh "mvnw package -DskipTests=true"


          }
        }
      }

  


 }



