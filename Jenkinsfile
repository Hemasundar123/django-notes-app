@Library('Shared')_
pipeline{
    agent { label 'Bleach'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            gitcheckout("https://github.com/Hemasundar123/django-notes-app/","main")
            }
        }
        stage("Code Build"){
            steps{
            build("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("notes-app","v1","mikey699")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
