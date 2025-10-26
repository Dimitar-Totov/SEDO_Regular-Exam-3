pipeline{
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages{
        stage("Install dependencies"){
            when{
                branch 'main'
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build"){
            when{
                branch 'main'
            }

            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Test"){
            when{
                branch 'main'
            }

            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}