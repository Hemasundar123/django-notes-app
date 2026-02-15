@Library('Mikey')_
pipeline{
    agent { label 'Bleach'}
    
    stages{
        stage("Start"){
            steps{
                echo "Start the CI"
            }
        }
        
        stage("Code clone"){
            steps{
                sh "whoami"
                gitcheckout("https://github.com/Hemasundar123/django-notes-app/","main")
            }
        }
        stage("Code Build"){
            steps{
                tagbuild("notes-app","v1")
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
