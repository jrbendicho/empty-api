stage ('Clean workspace') {
  steps {
    cleanWs()
  }
}
stage ('Git Checkout') {
  steps {
      git branch: 'master', credentialsId: 'ae16329b-775d-482d-9a11-3494817e5356', url: 'https://github.com/jrbendicho/empty-api.git'
    }
  }

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