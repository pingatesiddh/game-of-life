pipeline {
   agent {
    node {
        label 'linux'
        customWorkspace '/home/ec2-user'
    }
}

    stages {
        stage('checkout') {
            steps {
		sh '''
           git clone https://github.com/pingatesiddh/game-of-life.git
	   cd /home/ec2-user/game-of-life
		'''		
            }
        }
		stage('build') {
            steps {
                
            sh '''
		cd /home/ec2-user/
		mvn clean install
		''' 

            }
        }
        stage('Deploy') {
            steps {
            sh ' cp gameoflife-web/target/gameoflife.war  /mnt/apache-tomcat-9.0.80/webapps ' 
			
            }
        }		

    }
}
