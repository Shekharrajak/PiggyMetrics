pipeline {

	agent {
        	docker { image 'maven' }
    }
    environment {
        FOO = "BAR"
    }

    stages {
        stage("foo") {
            steps {
                sh 'echo "FOO is $FOO"'
		sh 'mvn clean package -DskipTests'
		sh "docker-compose -f docker-compose.yml -f docker-compose.dev.yml up"
            }
        }
    }
}
