pipeline {
   agent { 
       docker {
        image 'node:8.11.1' 
        args '-p 3000:3000'
   }}
   environment{
       CI = 'true'
   }
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
       stage('deliver'){
           steps{
               sh 'echo deliver it'
           }
       }
   }
   post{
       always{
           echo 'Test finished'
       }
       success{
            echo 'This will run only if successful'
            mail to: 'yangjun@nanchao.org',
                subject: "Passed Pipeline: ${currentBuild.fullDisplayName}",
                body: "Test succeeds with ${env.BUILD_URL}"
       }
       failure{
            echo 'This will run only if failed'
            mail to: 'yangjun@nanchao.org',
                subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                body: "Test failed with ${env.BUILD_URL}"
       }
   }
}
