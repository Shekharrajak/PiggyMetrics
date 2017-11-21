pipeline {
    environment {
        FOO = "BAR"
    }

    agent { label "master" }

    stages {
        stage("foo") {
            steps {
                sh 'echo "FOO is $FOO"'
		sh "docker-compose -f docker-compose.yml -f docker-compose.dev.yml up"
            }
        }
    }
}
