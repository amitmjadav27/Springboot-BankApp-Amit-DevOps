@Library('Shared')_

pipeline{
    agent {label 'jenkins-agent'}
    
    stages{
        stage("Code"){
            steps{
                clone("https://github.com/amitmjadav27/Springboot-BankApp-Amit-DevOps.git","dev")
                echo "Code clonning done."
            }
        }
        stage("Build"){                                                             
            steps{
                dockerbuild("bankapp-mini","latest")
                echo "Code build bhi hogaya."
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("DockerHubCreds","bankapp-mini","latest")
                echo "Push to dockerHub is also done."
            }
        }
        stage("Deplying"){
            steps{
                deploy()
                echo "Deployment bhi done."
            }
        }
    }
}
