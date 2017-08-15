node
{

    try
	{
    stage('select the branch')
	    {
	    if (env.BRANCH_NAME == 'development') 
			{
			 developBranch()
			}
	    if (env.BRANCH_NAME == 'master') 
			{
			 masterBranch()
			}
	    if (env.BRANCH_NAME == 'feature') 
			{
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

	def developBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'https://github.com/santoshdevops/multibranch.git'
       }
    
	stage('clean')
       {
	   
       sh "mvn clean"
       }
  
    stage('package')
      {
       sh "mvn package -DskipTests"
       }
	   
    stage('publish to artifactory')
       {
	   sh 'echo hello world'
	   }

	}
	
	
	
	def masterBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'ssh://git@coderepository.mcd.com:8443/sdkpil/identity-exp-api.git',credentialsId: '05de1113-6e45-4a34-8250-6f0f73f09267',branch: 'master'
       }
    
	stage('clean')
       {
	   
       sh "mvn clean"
       }
  
    stage('package')
      {
       sh "mvn package -DskipTests"
       }
	   
    stage('publish to artifactory')
       {
	   sh """
       cd target
	   mv mw-identity-exp-api-1.0.zip  mw-identity-exp-api-1.0.0-SNAPSHOT.zip
       mvn deploy:deploy-file -DgroupId=com.mcd -DartifactId=mw-identity-exp-api -Dversion=1.0.0-SNAPSHOT -Dpackaging=zip -Dfile=mw-identity-exp-api-1.0.0-SNAPSHOT.zip -DrepositoryId=apps-snapshot-local -Durl=http://artifactrepository.mcd.com/artifactory/list/apps-snapshot-local/com.mcd/mw-identity-exp-api/1.0.0-SNAPSHOT/
       """
	   }

	}
	
	def featureBranch() 
	{
 
    stage('clone stash')
       {
       git url: 'ssh://git@coderepository.mcd.com:8443/sdkpil/identity-exp-api.git',credentialsId: '05de1113-6e45-4a34-8250-6f0f73f09267',branch: 'feature'
       }
    
	stage('clean')
       {
	   
       sh "mvn clean"
       }
  
    stage('package')
      {
       sh "mvn package -DskipTests"
       }
	   
    stage('publish to artifactory')
       {
	   sh """
       cd target
	   mv mw-identity-exp-api-1.0.zip  mw-identity-exp-api-1.0.0-SNAPSHOT.zip
       mvn deploy:deploy-file -DgroupId=com.mcd -DartifactId=mw-identity-exp-api -Dversion=1.0.0-SNAPSHOT -Dpackaging=zip -Dfile=mw-identity-exp-api-1.0.0-SNAPSHOT.zip -DrepositoryId=apps-snapshot-local -Durl=http://artifactrepository.mcd.com/artifactory/list/apps-snapshot-local/com.mcd/mw-identity-exp-api/1.0.0-SNAPSHOT/
       """
	   }

	}
	

	def notifyBuild()
	{
	sh 'echo hello'
	}
	

