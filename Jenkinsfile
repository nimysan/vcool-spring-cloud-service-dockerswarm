pipeline {
    agent any

    stages {
        stage ('package Stage') {

            steps {
                withMaven(maven : 'm3') {
                    sh 'mvn clean package'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'm3') {
                    sh 'mvn test'
                }
            }
        }


        stage ('build docker image Stage') {
            steps {
                withMaven(maven : 'm3') {
                    sh 'mvn dockerfile:build'
                }
            }
        }
        
        stage ('run docker image Stage') {
        	steps {
        		sh 'docker run -d --restart=always -p 8088:8088 springio/vcool-spring-cloud-config-boot2'
        	}
        }
    }
}
