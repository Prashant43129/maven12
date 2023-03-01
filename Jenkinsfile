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
}
