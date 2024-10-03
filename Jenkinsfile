@Library('library')_

pipeline
{
    agent any
    stages
    {
        stage('MasterDownload')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('MasterBuild')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
        stage('MasterDeployment')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.88.112","testapp")
                }
            }
        }
        stage('MasterTesting')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativePipelinewithSharedLibraries")
                }
            }
        }
        stage('MasterDelivery')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.93.40","prodapp")
                }
            }
        }
    }
}









