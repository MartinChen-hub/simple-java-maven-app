pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args  '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Start') {
            echo "开始阶段"
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
