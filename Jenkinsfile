pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				bat 'mvn -B -DskipTests clean package'
			}
		}
		stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
		stage('codeQuality') {
            steps {
                bat 'mvn sonar:sonar'
            }
        }
		stage('deployement') {
            steps {
				sshagent(['f0817558-7410-4ccf-b86c-51332bb52245']) {
					bat 'sh scp target/ExcerciceCI.war localhost:8080/test/'
				}
            }
        }
	}
}