// Powered by Infostretch 

timestamps {

node () {

	stage ('freeStyle - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '8de30058-a7d5-48af-a291-6cb5bc7c3d76', url: 'https://github.com/jinglina/helloworld-java-feiteng.git']]]) 
	}
	stage ('freeStyle - Build') {
 			// Shell build step
sh """ 
#!/bin/sh
mvn clean install -DskipTests 
 """ 
	}
}
}