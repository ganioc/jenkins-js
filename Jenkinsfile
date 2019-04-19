pipeline {
   agent { 
       docker {
        image 'node:8.11.1' 
        args '-p 3000:3000'
   }}
   stages{
       stage('build'){
           steps{
               sh 'npm run start'
           }
       }
       stage('test'){
           steps{
               sh 'echo just a test'
           }
       }
   }
   post{
       always{
           echo 'Test finished'
       }
       success{
           echo 'This will run only if successful'
       }
       failure{
           echo 'This will run only if failed'
       }
   }
}
