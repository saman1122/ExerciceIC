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
				bat 'scp target/ExcerciceCI.war deployer:deployer@localhost:8080/test/'
            }
        }
	}
}