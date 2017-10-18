pipeline
{
    agent
    {
        docker
        {
            image 'praqma/native-gradle'
            args '-v $HOME/.m2:/home/jenkins/.m2'
            args '-v $HOME/.gradle:/home/jenkins/.gradle'
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
