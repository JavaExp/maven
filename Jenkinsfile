node('master') 
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/JavaExp/maven.git'             
    }
    stage('ContinuousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
sh 'scp /home/ubuntu/.jenkins/workspace/SP2/webapp/target/webapp.war ubuntu@172.31.17.144:/var/lib/tomcat8/webapps/testapp.war'
    }

}
