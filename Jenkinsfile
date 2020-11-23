pipeline {

   // Agent : Where You want yor code to be executed 
  agent any

   stages {
    // stage define the steps such as checkout,commit,build and deploy
      
	  stage('GIT CheckOut') {
	  	  steps {
            echo 'Checking out pipeline'
			git 'https://github.com/sforcloud/dockerhttpd.git'
       	   }
		    }
	 stage('BUILD'){
         steps {
            echo 'PipeLine started Building The Docker Image'
			sh label: '', script: 'sudo docker build -t pipeline .'
       	   }
		   }
		   
	  stage('TAG') {
         steps {
            echo 'Hello World! this is a Job2'
			sh label: '', script: 'sudo docker tag pipeline sforcloud/pipeline'
         }
      }
	  stage('LOGIN') {
         steps {
            echo 'We are logging in to docker HUb'
			sh label: '', script: 'sudo docker login -u sforcloud -p Asus!1234'
         }
   }
	  stage('PUSH') {
         steps {
           echo 'Pushing the Image to the Docker Hub'
		   sh label: '', script: 'sudo docker push sforcloud/pipeline'
		   
         }
   }

   }
   }
