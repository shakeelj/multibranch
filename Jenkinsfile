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
 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'A']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'id', url: 'https://github.com/santoshdevops/multibranch.git']]])      
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

       sh "cd A; /bin/mvn clean"

       sh "cd A; /bin/mvn package -DskipTests"

 
    }
    }
	
	
	 stage('feature')
    {
      
       when {
         branch 'feature'
      }
      
      steps {
                echo 'checking out feature'
 checkout([$class: 'GitSCM', branches: [[name: '*/feature']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'A']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'id', url: 'https://github.com/santoshdevops/multibranch.git']]])      
    }
    }
	
	}
	}
	
	
	
