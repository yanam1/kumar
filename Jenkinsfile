node {
    stage ("checkout")
    {
    checkout scm
    }
    stage ("maven")
    {
        sh ("mvn package")
    }
    stage ("sonar")
    {
        sh ("mvn sonar:sonar")
    }
    stage ("nexus")
    {
        sh ("mvn deploy")
    }
    stage ("tomcat")
    {
        sh ("cp /root/.jenkins/workspace/mavenpipe/target/*.war /opt/apache-tomcat-9.0.13/webapps")
    }
    stage ("email"){
        mail bcc: '', body: '''regrds 
girish''', cc: 'girishvitsece@gmail.com', from: '', replyTo: '', subject: 'mavenpipeline', to: 'girish4yu@gmail.com'


    }
    
}
