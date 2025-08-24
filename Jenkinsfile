@Library('Shared')_

pipeline{
    agent {label "Node1"}
    
    stages{
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/AdityaGaikwad6430/django-notes.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    build("notes-app", "latest", "dockerHubCreds")
                }
            }
        }
        stage("DockerPush"){
            steps{
                script{
                    dpush("notes-app","latest","dockerHubCreds")
                }
            }
        }
        stage("Test"){
            steps{
                echo "This is Testing the code "
                echo "Testing of code completed" 
            }
        }
        stage("Deploy"){
            steps{
                script{
                    deploy()
                }
            }
        }
    }
}
