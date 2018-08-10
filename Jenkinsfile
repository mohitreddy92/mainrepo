// Powered by Infostretch 

timestamps {

node () {

	stage ('bb - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/test']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GitHub', url: 'https://github.com/mohitreddy92/mainrepo.git']]]) 
	}
	stage ('bb - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.ws__cleanup.PreBuildCleanup". Please verify and convert manually if required.		// Shell build step
sh """ 
echo hello 
 """
// Unable to convert a build step referring to "org.jenkinsci.plugins.conditionalbuildstep.ConditionalBuilder". Please verify and convert manually if required. 
	}
	stage ('bb - Post build actions') {
/*
Please note this is a direct conversion of post-build actions. 
It may not necessarily work/behave in the same way as post-build actions work.
A logic review is suggested.
*/
		// Mailer notification
		step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'mohit.reddy92@gmail.com', sendToIndividuals: false])
 
	}
}
}