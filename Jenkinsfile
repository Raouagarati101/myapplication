node{
   stage('SCM Checkout'){
      git 'https://github.com/nesrinehm1996/my-application'
   }
   stage('Compile-Package'){
      //get maven home path 
      def mvnHome = tool name: 'maven-3', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
   
   stage('Archive') {
	      dir('build/target') {
	        archiveArtifacts artifacts: "${archiveName}", onlyIfSuccessful: true
	      }
	    }
	    if (branch != 'master') {
	      return
	}

}


