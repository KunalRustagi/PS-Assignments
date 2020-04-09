pipeline {
   agent any

   tools {
        maven 'Maven 3.6.3'
    }


      stages {

        stage('Checkout'){         
          steps{
              
              git branch: 'week-1', credentialsId: 'Github', url: 'https://github.com/KunalRustagi/PS-Assignments.git'
          }
        }
            stage('Build') {
             steps {
              
              sh "mvn -f /Users/kunal/PS-Assignments/week-1/pom.xml clean package"
              
            }
           }
         
         stage('Execute build'){
          steps{
            script {

              sh "java -jar /Users/kunal/PS-Assignments/week-1/target/assignment-1-1.0.jar > output.out"
              def output = readFile 'output.out'
              println(output)

            }

          }
        }
      }
    }
