@Library('Shared')_

pipeline{
    agent {label "Node1"}
    
    stages{
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/AdityaGaikwad6430/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    build()
                }
            }
        }
        stage("nginx"){
            steps{
                sh "sudo apt-get update && sudo apt install -y nginx"
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
