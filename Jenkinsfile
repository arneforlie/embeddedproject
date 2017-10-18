pipeline
{
    agent
    {
        docker
        {
            image 'praqma/native-gradle'
        }
    }
    stages
    {
        stage ('build')
        {
            steps
            {
                sh "uname -a"
                sh "ls -da /home/jenkins"
                sh "id -a"
                sh "./gradlew publishToMavenLocal"
            }
        }
        stage ('results')
        {
            steps
            {
                archiveArtifacts 'build/distributions/*.zip'
            }
        }
    }
}
