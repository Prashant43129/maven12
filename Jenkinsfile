node ('built-in')
{
    stage ("download")
    {
       git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage ("build")
    {
       sh 'mvn package'
    }
    stage ("deployment")
    {
       deploy adapters: [tomcat9(credentialsId: 'cc2fe471-3463-4f94-8daf-1749465d0147', path: '', url: 'http://172.31.17.240:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage ("testing")
    {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /var/lib/jenkins/workspace/scriptedpipeline3/testing.jar'
    }
    stage( "delivery")
    {
        deploy adapters: [tomcat9(credentialsId: 'cc2fe471-3463-4f94-8daf-1749465d0147', path: '', url: 'http://172.31.19.51:8080')], contextPath: 'liveapp', war: '**/*.war'
    }
}
