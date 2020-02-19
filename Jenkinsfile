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
     
       
        stage('copy') {
	   steps {
	     withAWS(region: 'us-east-1')
	     s3Upload(bucket:'s3repoartfacts',includePathPattern:'**/target/*.jar')
        
	    }

       }

     
     
     }


  }



