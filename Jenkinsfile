node('master') 
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/intelliqittrainings/maven.git'             
    }
    stage('ContinuousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
sh 'scp /home/ubuntu/.jenkins/workspace/SP2/webapp/target/webapp.war ubuntu@172.31.17.144:/var/lib/tomcat9/webapps/testapp.war'
    }

    stage('ContinuousTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/SP2/testing.jar'
    }
    stage('ContinuousDelivery')
    {
    
    sh 'scp /home/ubuntu/.jenkins/workspace/SP2/webapp/target/webapp.war ubuntu@172.31.21.131:/var/lib/tomcat9/webapps/prodapp.war'}
}
