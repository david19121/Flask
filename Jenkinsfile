pipeline{
    agent any
    stages{
         stage("GitHub checkout....") {
            steps {
                script {
 
                    git branch: 'main', url: 'https://github.com/david19121/Flask.git' 
                }
            }
        }
        stage("Build docker connect....."){
            steps{
                sh 'printenv'
                sh 'git version'
                sh 'docker build . -t david745/f-app1.0'
            }
        }
         stage("push image to DockerHub"){
            steps{

               script {
                  
                 withCredentials([string(credentialsId: 'david', variable: 'david')]) {
                    sh 'docker login -u david745 -p ${david}'
            }
              sh 'docker push david745/f-app1.0:latest'
            }
        }
    }
    }
}
