pipeline {
   agent any

   


      stages {

        stage('Checkout'){         
          steps{
              
              git branch: 'week-1', credentialsId: 'Github', url: 'https://github.com/KunalRustagi/PS-Assignments.git'
'            }
            }
            stage('Build') {
             steps {
              sh "mvn -Dmaven.test.failure.ignore=true clean package
            }
           }
         }
         stage('Execute build'){
          steps{
            script {

              sh "java -jar target/assignment-1-1.0.jar > output.out"
              def output = readFile 'output.out'
              println(output)

            }

          }
        }
      }
    }
