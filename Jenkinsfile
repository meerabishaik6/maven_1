node('master') 
{
   stage('continuous download ') 
   {
    git 'https://github.com/ArkLearnersEdge/maven.git'
   }
   stage('continuous build artifact ') 
   {
    sh 'mvn package'
   }
   stage('continuous deploy ') 
   {
    sh 'scp /home/ubuntu/.jenkins/workspace/development/webapp/target/webapp.war ubuntu@172.31.80.151:/var/lib/tomcat8/webapps/testapp.war'
   }
   stage('contineous Testing') 
   {
    git 'https://github.com/ArkLearnersEdge/FunctionalTesting.git'
    sh 'java -jar /home/ubuntu/.jenkins/workspace/development/testing.jar'
   }
   stage('continuous deploy to production ') 
   {
    sh 'scp /home/ubuntu/.jenkins/workspace/development/webapp/target/webapp.war ubuntu@172.31.88.206:/var/lib/tomcat8/webapps/testapp.war'
   }
}  
