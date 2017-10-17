pipeline
{
    agent any
    stages
    {
        stage ('checkout SCM')
        {
            steps
            {
                git 'https://github.com/arneforlie/embeddedproject'
            }
        }
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
