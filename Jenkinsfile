pipeline {
    agent any
    tools{
        maven 'maven'
    }
    
    stages{
        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Ayushrp/kubernetes.git']])
                sh 'mvn clean install'

            }
        }
         stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t luckymegha/kubernetes .'
                }
            }
        }
        stage('Push image to hub'){
            steps{
                script{
                    withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerhubpwd')]) {

                    sh 'docker login -u luckymegha -p ${dockerhubpwd}'
                        
                    }
                    sh 'docker push luckymegha/kubernetes'
                }
            }
        }
        stage('Deploy to K8s'){
            steps{
                script{
                    kubernetesDeploy (configs: 'deploymentservice.yaml', kubeconfigId: 'kubeconfig')
                }
            }
        }
    }
}
