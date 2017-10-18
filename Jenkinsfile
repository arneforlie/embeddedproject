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
