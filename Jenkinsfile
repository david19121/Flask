pipeline{
    agent any
    stages{
         stage("GitHub checkout....") {
            steps {
                script {
 
                    git branch: 'master', url: 'https://github.com/david19121/Flask.git' 
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
                  
                 withCredentials([string(credentialsId: 'davoo', variable: 'davoo')]) {
                    sh 'docker login -u david745 -p ${davoo}'
            }
              sh 'docker push david745/f-app1.0:latest'
            }
        }
    }
    }
}
