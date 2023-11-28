pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }	    
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
		}                
	}        
        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'Github', url: 'https://github.com/Ashwin261/register-app'
                }
        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
	        }    
        }	
        stage("Test Application"){
            steps {
                 sh "mvn test"
               }
        }
}
