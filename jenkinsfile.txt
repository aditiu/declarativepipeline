pipeline {
   agent any
     stages {
         stage("one"){
	     steps{
	     
	      bat "Hi i am compiling"
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
	             bat "Hello condition is false"
	         }
      
         }
	 stage("Four"){	
	       parallel{
	         stage("innerFour1"){	
	      
                     steps{
	                 bat "I am inner four1 stage "
	             }
      
                 }
		 stage("innerFour2"){	
	      
                     steps{
	                 bat "I am inner four2 stage "
	             }
      
                 }
	       }
               steps{
	            bat "I am outer four stage "
	       }
      
         }
    }
   bat 'aditi'
}
