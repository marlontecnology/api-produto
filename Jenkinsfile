pipeline {
    agent any        // Declararando qual agente vai utilizar. para usar qualquer agente, foi usado "any"

    stages {          // Declarando os stages, que são as etapas (estágios) da pipeline
        stage ('Build Image') {   //Stage para construção da imagem Docker
            steps {               // Declarando steps: Passos de execução do estágio
                script {
                    dockerapp = docker.build("marloncoutinho/api-produto:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }                
        }

        stage ('Push Image'){
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                         dockerapp.push('latest')
                         dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }
    }
}

