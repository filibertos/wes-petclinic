pipeline {

    agent any

    stages {
        stage("checkout") {
            steps {
                git url: 'git@github.com:filibertos/wes-petclinic.git', branch: 'main'
            }
        }
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
