#!/usr/bin/env groovy

pipeline {
    agent {label 'dev_lab_2'}

    options {
      buildDiscarder(logRotator(numToKeepStr: '10'))
      disableConcurrentBuilds()
      timeout(time: 1, unit: 'HOURS')
      timestamps()
    }

//    tools {}

    environment {
//      POM_VERSION = getVersion()
//      JAR_NAME = getJarName()
      AWS_ECR_REGION = 'eu-central-1'
//      AWS_ECS_SERVICE = 'ch-dev-user-api-service'
//      AWS_ECS_TASK_DEFINITION = 'ch-dev-user-api-taskdefinition'
//      AWS_ECS_COMPATIBILITY = 'FARGATE'
//      AWS_ECS_NETWORK_MODE = 'awsvpc'
//      AWS_ECS_CPU = '256'
//      AWS_ECS_MEMORY = '512'
//      AWS_ECS_CLUSTER = 'ch-dev'
//      AWS_ECS_TASK_DEFINITION_PATH = './ecs/container-definition-update-image.json'
    }

/*    stages {
        stage('Build & Test') {}

        stage('Build Docker Image') {}

        stage('Push Image to ECR') {}

        stage('Deploy in ECS') {}
    }
*/
//    post {}
}
