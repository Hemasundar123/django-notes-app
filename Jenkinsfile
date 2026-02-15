@Library('Mikey')
pipeline{
    agent { label 'Bleach'}

     triggers {
        githubPush()
    }
    
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
                tagbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("notes-app","latest","mikey699")
            }
        }
        stage("Deploy"){
            steps{
                echo "Deployed"
            }
        }
        
    }
}
