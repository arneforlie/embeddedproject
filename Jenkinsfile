pipeline
{
    agent https://hub.docker.com/r/praqma/native-make/
    stages
    {
        stage ('build')
        {
            steps
            {
                sh "make clean"
                sh "make all"
            }
        }
        stage ('test')
        {
            steps
            {
                sh "make test"
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
