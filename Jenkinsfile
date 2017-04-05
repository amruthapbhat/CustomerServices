   node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/amruthapbhat/CustomerServices.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      mvnHome = tool 'Maven'
   }

stage('Build') {
      // Run the maven build      
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
   }
      
      stage ('DockerBuild') {
         
       sh 'sudo Docker build -t amruthapbhat/customerservices .'
      }
}
