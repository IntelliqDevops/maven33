@Library('library')_

pipeline
{
    agent any
    stages
    {
        stage('LoansDownload')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('LoansBuild')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
    }
}









