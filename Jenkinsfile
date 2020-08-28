pipeline {
    
  environment {
    voteregistry = "prayag/voteapp"
    resultregistry = "prayag/resultapp"
    workerregistry = "prayag/workerapp"
    voteImage = ''
    resultImage = ''
    workerImage = ''
    }
  agent any
  stages{
/*    stage ('Build') {
      steps{
        echo "Building Project"
        sh './mvnw package'
      }
    }
    stage ('Archive') {
      steps{
        echo "Archiving Project"*/
    //    archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
    //  }
    //}
    stage ('Build Docker Image') {
      steps{
        echo "Building Docker Image"
        script {
          dir("vote"){
            sh "pwd"
            voteImage = docker.build(voteregistry)
          }
          resultImage = docker.build(resultregistry, "-f result/Dockerfile .")
          workerImage = docker.build(workerregistry, "-f worker/Dockerfile .")
        }
      }
    }
/*    stage ('Push Docker Image') {
      steps{
        echo "Pushing Docker Image"
        script {
          docker.withRegistry( '', registryCredential ) {
              dockerImage.push()
              dockerImage.push('latest')
          }
        }
      }
    }
    stage ('Deploy to Dev') {
      steps{
        echo "Deploying to Dev Environment"
        sh "docker rm -f petclinic || true"
        sh "docker run -d --name=petclinic -p 8081:8080 prabhavagrawal/petclinic"
      }
    }*/
  }
}
