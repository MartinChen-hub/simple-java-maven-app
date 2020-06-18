pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args  '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('运行 Kubectl') {
            steps {
                sh './jenkins/scripts/k8s-deploy-admin-api.sh'
                sh './jenkins/scripts/k8s-deploy-wx-api.sh'
            }
        }
    }

}
