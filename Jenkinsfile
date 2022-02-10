node('Dev') 
{
    stage('continuousdownload_ loans') 
    {
       git 'https://github.com/fres0221/Maven_fareed.git'
    }
    stage('continuousbuild_ loans') 
    {
       sh 'mvn package'
    }
    stage('continuousdeployment_ loans') 
    {
       sh 'scp /home/ubuntu/.jenkins/workspace/Multipipeline-2/webapp/target/webapp.war ubuntu@172.31.80.110:/var/lib/tomcat8/webapps/testing.war'
    }
    stage('continuoustesting_ loans') 
    {
       git 'https://github.com/fres0221/functionaltesting_212.git'
       sh 'java -jar /home/ubuntu/.jenkins/workspace/Multipipeline-2/testing.jar'
    }
    stage('continuousdelivery_ loans') 
    {
       sh 'scp /home/ubuntu/.jenkins/workspace/Multipipeline-2/webapp/target/webapp.war ubuntu@172.31.85.10:/var/lib/tomcat8/webapps/prod.war'
    }
    
}
