pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Baixa o código do seu GitHub
                checkout scm
            }
        }

        stage('Validar HTML') {
            steps {
                echo 'Iniciando validação do index.html...'
                
                // Comando que procura a tag <body> no arquivo. 
                // Se não encontrar, o comando 'grep' retorna erro e para o pipeline.
                sh "grep -q '<body>' index.html"
                
                echo 'Sucesso: O arquivo index.html contém a tag <body>!'
            }
        }

        stage('Deploy Simulado') {
            steps {
                echo 'HTML validado! Fingindo que estou enviando para o servidor...'
                echo 'Site atualizado com sucesso 🚀'
            }
        }
    }
}