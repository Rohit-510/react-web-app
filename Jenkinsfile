
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
           cleanWs()
           checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'chaudhary.rohit510@gmail.com', url: 'https://github.com/vmgponly/react-web-app.git']]])
           sh '''
           ls-ltr
           npm install
           npm run build
           ls -ltr
           cd build/
           ls -ltr
           tar -cvf frontend-${BUILD_NUMBER}.tar *
           cp frontend-${BUILD_NUMBER}.tar ${WORKSPACE}/
           ls -ltr
           '''
        }
      }
    }
    stage('Deploy')
    {
      steps
      {
         sh '''
         rm -rf deploy
         mkdir deploy
         cp -r frontend-${BUILD_NUMBER}.tar deploy/
         cd deploy
         tar -xvf frontend-${BUILD_NUMBER}.tar
         ls -ltr
         '''
      }
    }
  }

}
