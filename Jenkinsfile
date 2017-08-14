node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   sh 'echo $GIT_BRANCH'
   sh 'echo $(git branch)'

   // Checkout code from repository
   checkout scm

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.
 //  def mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "/bin/mvn clean install"
}
