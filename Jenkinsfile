pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent any
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "windows_slave1"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "windows_slave2"
                    }
                    steps {
			echo "Task1 on Master"
		   }
                }
            }
        }
    }
}
