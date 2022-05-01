pipeline{
    agent any 
     tools { 
        maven 'Maven' 
    }

    stages{
        stage("project-maven-test"){
            steps{
                sh  ' mvn test '
                
            }
            
            }
            stage("project-maven-build"){
            steps{
                sh 'mvn package'
                
            }
            
            }
            stage("building docker image"){
            steps{
                
                script{
                sh   ' docker login -u lakshit45 -p sslakshit45'
                sh   'docker build -t lakshit45/img . '

                }
                 
            }
            
            }
            
            stage("building  image"){
            steps{
                
                script{
                sh ' docker login -u lakshit45 -p sslakshit45 ' 
                sh   'docker push  lakshit45/img '

                }
                 
            }
            
            
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
