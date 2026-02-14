pipeline {
    agent any

    options {
        disableConcurrentBuilds()
    }

    environment {
        IMAGE_NAME = "juhisinha/multibranch-flask-app"
        GIT_USER   = "juhisinha422"
        GIT_EMAIL  = "juhisinha422@gmail.com"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Push Image') {
            when { branch 'main' }
            steps {
                script {
                    env.IMAGE_TAG = "build-${BUILD_NUMBER}"

                    withCredentials([usernamePassword(
                        credentialsId: 'dockerhub-creds',
                        usernameVariable: 'DOCKER_USER',
                        passwordVariable: 'DOCKER_PASS'
                    )]) {
                        sh """
                        docker build -t ${IMAGE_NAME}:${IMAGE_TAG} .
                        echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                        docker push ${IMAGE_NAME}:${IMAGE_TAG}
                        """
                    }
                }
            }
        }

        stage('Update K8s Manifest') {
            when { branch 'main' }
            steps {
                script {
                    withCredentials([usernamePassword(
                        credentialsId: 'github-creds',
                        usernameVariable: 'GIT_USERNAME',
                        passwordVariable: 'GIT_TOKEN'
                    )]) {
                        sh """
                        set -e
                        git config user.name "$GIT_USER"
                        git config user.email "$GIT_EMAIL"

                        git fetch origin
                        git checkout main
                        git reset --hard origin/main

                        sed -i "s|image:.*|image: ${IMAGE_NAME}:${IMAGE_TAG}|" k8s/deployment.yml

                        git add k8s/deployment.yml
                        git diff --cached --quiet || git commit -m "Updated image to ${IMAGE_TAG}"
                        git push https://${GIT_USERNAME}:${GIT_TOKEN}@github.com/juhisinha422/Production-Grade-CI-CD-Pipeline-using-Jenkins-Multibranch-GitOps.git
                        """
                    }
                }
            }
        }
    }
}
