pipeline{
    agent any
    tools { 
        maven 'maven3'
    }
    stages
       {
            stage("clean")
            {
                steps{
                    sh "mvn clean"
                }
            }
            stage("Build")
            {
                steps{
                    sh "mvn compile"
                }
                
            }
            stage("TEST")
            {
                steps{
                    sh "mvn test"
                }
            }
            stage("package")
            {
                steps{
                    sh "mvn package"
                }
            }
           stage("Deploys")
            {
                steps{
                    sshagent(['kunal8077']) {
                    sh "scp -o StrictHostKeyChecking=no  /var/lib/jenkins/workspace/jenkinsassignment1_prod/target/*.jar ubuntu@3.87.221.20:/home/ubuntu/"
                               
                 }
                }
            }
       }
}
        
    
   
