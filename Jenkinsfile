	node {
		stage('Clean') {
		 sh 'mvn clean'
			 }

		 stage('Build') 
		 {
			if (env.BRANCH_NAME == 'develop') 
			{
				echo 'I only execute on the develop branch'
				git url: 'https://github.com/santoshdevops/multibranch.git'
				sh "/bin/mvn clean"
				sh "/bin/mvn package -DskipTests"
				
			} else 
			{
				echo 'I execute elsewhere'
			}
			
			
			if (env.BRANCH_NAME == 'master') 
			{
				echo 'I only execute on the master branch'
				git url: 'https://github.com/santoshdevops/multibranch.git'
				sh "/bin/mvn clean"
				sh "/bin/mvn package -DskipTests"
				
			} else 
			{
				echo 'I execute elsewhere'
			}
			
			if (env.BRANCH_NAME == 'feature') 
			{
				echo 'I only execute on the feature branch'
				git url: 'https://github.com/santoshdevops/multibranch.git'
				sh "/bin/mvn clean"
				sh "/bin/mvn package -DskipTests"
				
			} else 
			{
				echo 'I execute elsewhere'
			}
			
			
			
		}	
		
		
		
		stage('deploy') 
		{
			if (env.BRANCH_NAME == 'master') 
			{
				echo 'I only execute on the master branch'
				git url: 'https://github.com/santoshdevops/multibranch.git'
				sh "/bin/mvn package -DskipTests"
				
			} else 
			{
				echo 'I execute elsewhere'
			}
			
			
			if (env.BRANCH_NAME == 'development') 
			{
				echo 'I only execute on the development branch'
				git url: 'https://github.com/santoshdevops/multibranch.git'
				sh "/bin/mvn package -DskipTests"
				
			} else 
			{
				echo 'I execute elsewhere'
			}
		
		
		if (env.BRANCH_NAME == 'feature') 
			{
				echo 'I only execute on the feature branch'
				git url: 'https://github.com/santoshdevops/multibranch.git'
				sh "/bin/mvn package -DskipTests"
				
			} else 
			{
				echo 'I execute elsewhere'
			}
		
		
			
		}
		
		
		}
		
		
			
		
		
		
		
		
