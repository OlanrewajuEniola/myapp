pipeline {
    agent any

    tools {
	jdk 'JDK17'
        maven 'Maven'   // Name must match what you configured in Jenkins global tools
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/OlanrewajuEniola/myapp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                // Copy WAR to Tomcat webapps directory
                sh 'sudo cp target/myapp-1.0-SNAPSHOT.war /opt/tomcat10/webapps/myapp.war'
            }
        }
    }
}

