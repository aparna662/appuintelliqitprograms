





















node('master')
{
stage("continuousdownload")
{
git 'https://github.com/intelliqittrainings/maven.git'   
}
stage("continuousbuild")
{
sh label: '', script: 'mvn package'   
}
stage("continuousdeployment")
{
sh label: '', script: 'scp  /home/ubuntu/.jenkins/workspace/sp/webapp/target/webapp.war ubuntu@172.31.13.18:/var/lib/tomcat8/webapps/testapp1.war'    
}
stage("continuoustesting")
{
git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/sp/testing.jar'
}
stage("continuousdelivery")
{
sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/sp/webapp/target/webapp.war ubuntu@172.31.3.250:/var/lib/tomcat8/webapps/prodapp1.war'
}
}



   
   

