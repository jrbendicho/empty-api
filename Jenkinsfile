stage('Restore packages'){
   steps{
      bat "dotnet restore empty-api\\empty-api.csproj"
     }
  }

  stage('Clean'){
    steps{
        bat "dotnet clean restore empty-api\\empty-api.csproj"
     }
   }

   stage('Build'){
   steps{
      bat "dotnet build empty-api\\empty-api.csproj --configuration Release"
    }
 }

 stage('Publish'){
     steps{
       bat "dotnet publish empty-api\\empty-api.csproj "
     }
}