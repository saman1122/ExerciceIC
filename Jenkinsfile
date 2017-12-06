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
				bat 'cp target/ExcerciceCI.war "C:/Program Files/Apache Software Foundation/Tomcat 7.0/webapps/"'
            }
        }
	}
}