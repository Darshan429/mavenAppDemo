pipeline{
  agent any
  tools{
    maven 'MAVEN'
  }
  stages{
    stage('Checkout'){
      steps{
      git branch:'main' ,url:'https://github.com/Darshan429/mavenAppDemo.git'
      }
    }

    stage('Build'){
      steps{
       sh 'mvn clean package'
      }
    }

    stage('Test'){
      steps{
      sh 'mvn test'
      }
    }

    stage('Runapplication'){
      steps{
        sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar
      }
      
  }
}
  post{
    success{
      echo "Built and deployment successfull"
    }
    failure{
      echo "Failure!"
    }
  }
}
