pipeline {
    agent any
    stages{
        stage("checkout") {
            steps{
            sh "ls"
            echo "Before git"
            git branch:"main", url:"https://github.com/abdelrahmanzidan164-hue/pet-clinic2"
            echo "AFter git"
            sh "ls"
            }
    }
        stage("Build"){
            steps{
                sh "./mvnw package"
            }
        }
        stage("Capture"){
            steps{
                archiveArtifacts artifacts: '**/target/*.jar'
                junit '**/target/surefire-reports/TEST*.xml'
                jacoco()
            }
        }
    }
}
