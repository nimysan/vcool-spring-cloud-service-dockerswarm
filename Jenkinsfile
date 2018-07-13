pipeline {
    agent any

    stages {
        stage ('run docker image Stage') {
        	steps {
        		sh 'docker stack deploy -c docker-compose.yml vcool-microservice-stack'
        	}
        }
    }
}
