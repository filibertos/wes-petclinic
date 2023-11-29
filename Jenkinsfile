pipeline {

    agent any

    stages {
        stage("build") {
            steps {
                sh './mvnw clean package'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/TEST*.xml'
            jacoco()
            archiveArtifacts 'target/*.jar'
        }
    }
}
