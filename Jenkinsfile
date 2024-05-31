pipeline {
    agent any        // Declararando qual agente vai utilizar. para usar qualquer agente, foi usado "any"

    stages {          // Declarando os stages, que sao as etapas (estágios) da pipeline
        stage ('Build Image') {   //Stage para construção da imagem Docker
            steps {               // Declarando steps: Passos de execução do estágio
                script {
                    dockerapp = docker.build("marloncoutinho/api-produto", '-f ./src/Dockerfile ./src')
                  }
                }                
            }
        }
}

