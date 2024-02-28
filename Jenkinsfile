node {

   def registryProjet='forma-fred/'
   def IMAGE="${registryProjet}app:${version}"

    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
          }

    stage('Run') {
          img.withRun("--name run-$BUILD_ID") { c ->
       
          }
    }

    stage('Push') {
       docker.withRegistry('https://registry.ludovic.io/' , 'registry_id') {
              img.push 'latest'
              img.push()
          }
    }

}

