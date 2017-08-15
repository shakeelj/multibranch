node 
{
    try
	{
    stage('select the branch')node 
{
    try
	{
    stage('select the branch')
	    {
	    if (env.BRANCH_NAME == 'development') 
			{
			//calling the function developBranch if develop branch is getting built
			 developBranch()
			}
	    if (env.BRANCH_NAME == 'master') 
			{
			//calling the function masterBranch if master branch is getting built
			 masterBranch()
			}
	    //if (env.BRANCH_NAME && env.BRANCH_NAME.matches("featur*/*") ) 
		if (env.BRANCH_NAME =~ feature([a-z]+) ) 
			{
			//calling the function featureBranch if feature branch is getting built
			sh "echo hello world 123"
			sh "echo ${env.BUILD_NUMBER} "
			 featureBranch()
			}
		}	
		
	} 
	catch(e) 
	{
    currentBuild.result = "FAILED"
    throw(e)
    } 
    finally 
    {
   
    notifyBuild()
    }	
		
		
}
// function defination for developBranch
//// build using maven, run the tests, push it to artifactory with SNAPSHOT-1.0.0 as the version  	
	def developBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "echo cleandevelop"
       }
  
    stage('package')
      {
       sh "echo packagedevelop "
       }
	   
    stage('publish to artifactory')
       {
	   sh 'echo publish to arti develop'
	//   sh """
     //  cd target
// there is issue in pom.xml which needs to be corrected by dev, so using work around for now
	   
	  // mv mw-identity-exp-api-1.0.zip  mw-identity-exp-api-1.0.0-SNAPSHOT.zip
      // mvn deploy:deploy-file -DgroupId=com.mcd -DartifactId=mw-identity-exp-api -Dversion=1.0.0-SNAPSHOT -Dpackaging=zip -Dfile=mw-identity-exp-api-1.0.0-SNAPSHOT.zip -DrepositoryId=apps-snapshot-local -Durl=http://artifactrepository.mcd.com/artifactory/list/apps-snapshot-local/com.mcd/mw-identity-exp-api/1.0.0-SNAPSHOT/
     //  """
	   }

	}
	
// function defination for masterBranch	
	
// build using maven, run the tests, push it to artifactory with jenkins build number as the version 	
	def masterBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "echo masterclean"
       }
  
    stage('package')
      {
       sh "echo packagemaster"
       }
	   
    stage('publish to artifactory')
       {
	     sh """ 'echo masterpublishtorepos
		 echo {env.BUILD_NUMBER}
		 """
		 
	   //sh """
       //cd target
	   //mv mw-identity-exp-api-1.0.zip  mw-identity-exp-api-1.0.0-{env.BUILD_NUMBER}.zip
       //mvn deploy:deploy-file -DgroupId=com.mcd -DartifactId=mw-identity-exp-api -Dversion=1.0.0-{env.BUILD_NUMBER} -Dpackaging=zip -Dfile=mw-identity-exp-api-1.0.0-{env.BUILD_NUMBER}.zip -DrepositoryId=apps-snapshot-local -Durl=http://artifactrepository.mcd.com/artifactory/list/apps-snapshot-local/com.mcd/mw-identity-exp-api/1.0.0-SNAPSHOT/	  

	  // ${BUILD_NUMBER}
      // mvn -B release:prepare 
	  // mvn -B release:perform
	  // mvn release:update-versions -DautoVersionSubmodules=true
       //"""
	   }

	}

// function defination for featureBranch	
////// build using maven, run the tests, send mails to team.
	
	def featureBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "echo cleanfeature"
       }
  
    stage('package')
       {
       sh "echo packagefeature"
       }
	
    }
	
	
	

	def notifyBuild()
	{
	sh 'echo hello'
	}
	
	
	 



	    {
	    if (env.BRANCH_NAME == 'development') 
			{
			//calling the function developBranch if develop branch is getting built
			 developBranch()
			}
	    if (env.BRANCH_NAME == 'master') 
			{
			//calling the function masterBranch if master branch is getting built
			 masterBranch()
			}
	    if (env.BRANCH_NAME && env.BRANCH_NAME.matches("feat/*") ) 
			{
			//calling the function featureBranch if feature branch is getting built
			sh "echo hello world 123"
			sh "echo ${env.BUILD_NUMBER} "
			 featureBranch()
			}
		}	
		
	} 
	catch(e) 
	{
    currentBuild.result = "FAILED"
    throw(e)
    } 
    finally 
    {
   
    notifyBuild()
    }	
		
		
}
// function defination for developBranch
//// build using maven, run the tests, push it to artifactory with SNAPSHOT-1.0.0 as the version  	
	def developBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "echo cleandevelop"
       }
  
    stage('package')
      {
       sh "echo packagedevelop "
       }
	   
    stage('publish to artifactory')
       {
	   sh 'echo publish to arti develop'
	//   sh """
     //  cd target
// there is issue in pom.xml which needs to be corrected by dev, so using work around for now
	   
	  // mv mw-identity-exp-api-1.0.zip  mw-identity-exp-api-1.0.0-SNAPSHOT.zip
      // mvn deploy:deploy-file -DgroupId=com.mcd -DartifactId=mw-identity-exp-api -Dversion=1.0.0-SNAPSHOT -Dpackaging=zip -Dfile=mw-identity-exp-api-1.0.0-SNAPSHOT.zip -DrepositoryId=apps-snapshot-local -Durl=http://artifactrepository.mcd.com/artifactory/list/apps-snapshot-local/com.mcd/mw-identity-exp-api/1.0.0-SNAPSHOT/
     //  """
	   }

	}
	
// function defination for masterBranch	
	
// build using maven, run the tests, push it to artifactory with jenkins build number as the version 	
	def masterBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "echo masterclean"
       }
  
    stage('package')
      {
       sh "echo packagemaster"
       }
	   
    stage('publish to artifactory')
       {
	     sh """ 'echo masterpublishtorepos
		 echo {env.BUILD_NUMBER}
		 """
		 
	   //sh """
       //cd target
	   //mv mw-identity-exp-api-1.0.zip  mw-identity-exp-api-1.0.0-{env.BUILD_NUMBER}.zip
       //mvn deploy:deploy-file -DgroupId=com.mcd -DartifactId=mw-identity-exp-api -Dversion=1.0.0-{env.BUILD_NUMBER} -Dpackaging=zip -Dfile=mw-identity-exp-api-1.0.0-{env.BUILD_NUMBER}.zip -DrepositoryId=apps-snapshot-local -Durl=http://artifactrepository.mcd.com/artifactory/list/apps-snapshot-local/com.mcd/mw-identity-exp-api/1.0.0-SNAPSHOT/	  

	  // ${BUILD_NUMBER}
      // mvn -B release:prepare 
	  // mvn -B release:perform
	  // mvn release:update-versions -DautoVersionSubmodules=true
       //"""
	   }

	}

// function defination for featureBranch	
////// build using maven, run the tests, send mails to team.
	
	def featureBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "echo cleanfeature"
       }
  
    stage('package')
       {
       sh "echo packagefeature"
       }
	
    }
	
	
	

	def notifyBuild()
	{
	sh 'echo hello'
	}
	
	
	 


