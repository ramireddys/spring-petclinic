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
     
        
post {
               always {
                       //show junit test results
                       junit 'target/surefire-reports/*.xml'
               } 
               success {
                       //push artifacts to s3 bucket (.jar)
                       script {
                              
			      withAWS(region: 'us-east-1') 
			      }

		{	      
             s3Upload(bucket:'s3repoartfacts',includePathPattern:'**/target/*.jar')
             
	     } 
	   } 
       
   }

        
	
	 }


  }



