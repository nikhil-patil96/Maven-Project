pipeline{
	agent any
	
	
	tools
	{
		jdk "java-local"
		maven "mvn-local"
	}
	
	stages
	{
		
		stage("Git checkout")
		{
			steps
			{
				checkout scm
			}
		}
		/*
		stage("Sonarqube analysis")
		{
			steps
			{
				bat '''
					echo "================Sonarqube Analysis==================="
					echo "mvn sonar:sonar"
				'''
			}
		}*/
		stage("Unit Test")
		{
			steps
			{
				sh '''
					echo "================Unit Test==================="
					echo "mvn test"
				'''
			}
		}
		stage("Code coverage")
		{
			steps
			{
				sh '''
					echo "================Sonarqube Analysis==================="
					echo "mvn cobertura:cobertura"
				'''
			}
		}
		stage("Compile")
		{
			steps
			{
				sh '''
					echo "=============== Cleaning and Compiling ================"
					mvn compile
				'''
			}
		}
		
		stage("Package")
		{
			steps
			{
				sh '''
					echo "=============== packaging ================"
					mvn clean package
				'''
			}
		}
		
		stage("Deploy")
		{
			steps
			{
				sh '''
					echo "=============== Cleaning and Compiling ================"
							
				'''
			}
		}
	}
	/*
	post
	{
		always
		{
			bat '''
				echo "This is Post build action - Always"
			'''
		}
		success
		{
			bat '''
				echo "This is Post build action - Success"
			
			'''
			*/
			//archiveArtifacts artifacts: '**/*', onlyIfSuccessful: true
			/*
			build job: 'Deploy_To_UCD'
		}
	}*/

}
