pipeline {
  
agent any
      
stages  {
    
stage('master')
    {
      
       when {
         branch 'master'
      }
      
      steps {
                echo 'checking out master'

       git url: 'https://github.com/santoshdevops/multibranch.git'

       sh "/bin/mvn clean"

       sh "/bin/mvn package -DskipTests"

 
    }
    }



	
	 stage('development')
    {
      
       when {
         branch 'development'
      }
      
      steps {
                echo 'checking out development'

       git url: 'https://github.com/santoshdevops/multibranch.git'

       sh "/bin/mvn clean"

       sh "/bin/mvn package -DskipTests"

 
    }
    }
	
	
	 stage('feature')
    {
      
       when {
         branch 'feature'
      }
      
         steps {
                echo 'checking out feature'

       git url: 'https://github.com/santoshdevops/multibranch.git'

       sh "/bin/mvn clean"

       sh "/bin/mvn package -DskipTests"

 
    }
    }
	
	}
	}
	
	
	
