pipeline {
    agent any
   
    stages {
      stage('clone the code'){
        steps{
          git 'https://github.com/MrinalCode/selenium-testng-demo-project.git'
        }
      }

      stage('build the code'){
        steps{
          sh 'mvn clean package -Dskiptests'
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
