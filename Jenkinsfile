pipeline
{

  agent any

 
  tools
  {
    nodejs 'node' 

      }

 
  stages
  {
   stage('Build')
    {
     
      steps
      {
       
        script
        {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'chaudhary.rohit510@gmail.com', url: 'https://github.com/vmgponly/react-web-app.git']]])
        }
      }

    }  

  }  

}  
   
