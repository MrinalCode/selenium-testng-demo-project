pipeline {
    agent { label 'JDK17' }
   
    stages { 

      stage('build the code'){
        steps{
          sh 'mvn clean package'
         }
      }
      
      stage('test it'){
        steps{
          sh 'mvn test'
         }
      }      
      
      stage('Publish Reports') {
       steps {
         echo "Publishing TestNG Reports..."
         junit 'target/surefire-reports/*.xml'
    }
   }
   }
  
   post{
      always{
        echo 'test completed'
        }
   }
}
