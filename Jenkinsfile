pipeline {
   agent any
     stages {
         stage("one"){
	     steps{
	     
	      sh "Hi i am compiling"
             }	
	  }	 	
         stage("Two"){
             steps{
	        input("input required from users to proceed")
	     }
            
         }	
         stage("Three"){
	         when{
	               not{
		           branch "master"
		       }
		 }
                 steps{
	             sh "Hello condition is false"
	         }
      
         }
	 stage("Four"){	
	       parallel{
	         stage("innerFour1"){	
	      
                     steps{
	                 sh "I am inner four1 stage "
	             }
      
                 }
		 stage("innerFour2"){	
	      
                     steps{
	                 sh "I am inner four2 stage "
	             }
      
                 }
	       }
               steps{
	            sh "I am outer four stage "
	       }
      
         }
    }
   bat 'echo aditi'
}
