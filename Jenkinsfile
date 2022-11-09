pipeline {
  agent any
  stages {
    stage('Build Application') { 
      steps {
        sh 'mvn clean install'
      }
    }
 	stage('Test') { 
      steps {
        echo 'Test Appplication...' 
        sh 'mvn test'
      }
    }
 	
   
	stage('Deploy CloudHub') { 
//       environment {
//         ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
//       }
            
      steps {
        echo 'Deploying only because of code commit...'
        echo 'Deploying to  dev environent....'
        sh 'mvn package deploy -DmuleDeploy -Dusername=varsha_p -Dpassword=C@yogita2809 -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
      }
	  
	}
  }
}
