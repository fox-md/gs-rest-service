pipeline {
    agent {
        label 'mvn36-jdk8-attached'
    }
    stages {
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Publish jacoco') {
            steps {
                jacoco()
                publishCoverage adapters: [jacocoAdapter('complete/target/site/jacoco/jacoco.xml')]
            }
        }
    }
}
