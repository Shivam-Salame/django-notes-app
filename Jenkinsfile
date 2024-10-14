@Library("Shared") _
pipeline {
    agent any
    
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                clone("https://github.com/Shivam-Salame/django-notes-app", "main")
            }
        }
        stage("Build"){
            steps{
            docker_build("notes-app","latest","shivamsalame")
            }
        }
        stage("Push to Docker Hub"){
            steps{
                docker_push("notes-app","latest","shivamsalame")
                }
        }
        stage("Deploy"){
            steps{
                docker_compose()
            }
        }
    }
}
