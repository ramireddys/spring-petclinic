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
              post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }     
                 
                 
                 
                 
                 
        }
     
        
       stage(upload) {
         steps {  
		         
                                                               
			      
             s3Upload(enties: [[bucket: "s3repoartfacts", sourceFile: "/var/lib/jenkins/workspace/pipeline project/target/spring-petclinic-2.2.0.BUILD-SNAPSHOT.jar", selectedRegion: "us-east-1", managedArtifacts: true, flatten: true]]  )
	    } 
	   } 
       
   

        
	
	 }


  }



