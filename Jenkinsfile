pipeline {
    agent none
    stages {
        stage('None-parallel stage') {
            agent {
                label 'master'
            }
            steps {
                    echo "First stage of execution!";
            }
    	}
        stage('Run Tests') {
            parallel {
                stage('Test on Windows-slave') {
                    agent {
                        label 'Windows-slave'
                    }
                    steps {
                             echo "Task1 on agent - Windows-slave";
                    }
 		}
                stage('Test on Windows_Node') {
                    agent {
                        label 'Windows_Node'
                    }
                    steps {
                             echo "Task2 on agent - Windows_Node";
                    }
 	        }
                stage('Test on master') {
                    agent {
                        label 'master'
                    }
                    steps {
                             echo "Task3 on agent - master";
                    }
                }
            }
        }
    }
}
