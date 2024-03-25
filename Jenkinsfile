pipeline {
    agent any
    tools {
        maven 'maven'
    }
    environment {
        SCANNER_HOME = tool 'sonar-scanner'
        APP_NAME = "java-registration-app"
        RELEASE = "1.0.0"
        DOCKER_USER = "ashfaque9x"
        DOCKER_PASS = 'dockerhub'
        IMAGE_NAME = "${DOCKER_USER}" + "/" + "${APP_NAME}"
        IMAGE_TAG = "${RELEASE}-${BUILD_NUMBER}"
	
    }
    stages {
         stage('clean workspace') {
            steps {
                cleanWs()
            }
         }
         stage('Checkout from Git') {
            steps {
                git branch: 'main', url: 'https://ashfaque-9x@bitbucket.org/vtechbox/registration-app.git'