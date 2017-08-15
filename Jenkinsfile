
  
   node {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'A']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'id', url: 'https://github.com/santoshdevops/multibranch.git']]])
    stage('A') {
      
      steps {
                echo 'checking out master'
        when {
         branch 'master'
      }
    }
    }
    checkout([$class: 'GitSCM', branches: [[name: '*/development']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'B']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'id', url: 'https://github.com/santoshdevops/multibranch.git']]])
   stage('B') {
     
      steps {
         when {
         branch 'development'
      }
        
        echo 'checking out dev'
    }
    }
checkout([$class: 'GitSCM', branches: [[name: '*/feature']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'C']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'id', url: 'https://github.com/santoshdevops/multibranch.git']]])
    stage('C') {
    
      steps {
          when {
         branch 'feature'
      }
        echo 'checking out feature'
    }
    }

    }
