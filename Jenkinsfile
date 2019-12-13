node('master') 
{
  try 
  {
    stage('build') 
    {
      git url: 'git@github.com:gfriel2104/coursework_2.git'
      
      sh "./develop server.js
    }
   }
   
   stage('Sonarqube') 
   {
      environment 
      {
          scannerHome = tool 'SonarQubeScanner'
      }
      steps 
      {
          withSonarQubeEnv('sonarqube') 
          {
              sh "${scannerHome}/bin/sonar-scanner"
          }
          timeout(time: 10, unit: 'MINUTES') 
          {
              waitForQualityGate abortPipeline: true
          }
      }
    }
}
