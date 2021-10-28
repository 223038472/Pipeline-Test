node
{
def mavenHome = name: "maven3.6.6"
  
    stage("1. git clone")
    {
       git credentialsId: 'GitCredentials', url: 'https://github.com/223038472/Pipeline-Test'
    }
  
    stage("2. Build")
    {
        sh "${mavenHome}/bin/mvn clean package"
    }
  
    stage("3. SonarQubeReport")
    {
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
  
    stage("4. Nexus")
    {
        sh "${mavenHome}/bin/mvn deploy"
    }
}
  
  
