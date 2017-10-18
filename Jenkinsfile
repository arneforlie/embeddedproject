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
                sh "gradlew publishToMavenLocal"
            }
        }
        stage ('results')
        {
            steps
            {
                archiveArtifacts 'out/bin/main'
                junit '**/out/bin/results_junit.xml'
            }
        }
    }
}
