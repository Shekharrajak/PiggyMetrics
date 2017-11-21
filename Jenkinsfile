pipeline {

    agent none
    environment {
        FOO = "BAR"
    }

    stages {
	stage("packaging"){
		agent {
        		docker { image 'maven' }
    		}
		steps {
                	sh 'mvn clean package -DskipTests'
            }
	}
        stage("foo") {
		agent any
            steps {
                sh 'echo "FOO is $FOO"'
		sh "docker-compose -f docker-compose.yml -f docker-compose.dev.yml up"
            }
        }
    }
}
