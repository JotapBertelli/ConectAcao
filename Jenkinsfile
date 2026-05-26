pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Baixa a versão mais recente do código do seu GitHub
                checkout scm
            }
        }

        stage('Build Docker') {
            steps {
                echo 'Iniciando o build da imagem Docker...'
                // Cria a imagem Docker chamada 'site-social' com base no Dockerfile
                sh 'docker build -t site-social .'
            }
        }

        stage('Remover Container Antigo') {
            steps {
                echo 'Removendo containers antigos para evitar conflitos de porta...'
                // Remove o container antigo se ele existir
                sh 'docker rm -f site-social || true'
            }
        }

        stage('Subir Novo Container') {
            steps {
                echo 'Iniciando o novo container na porta 8081...'
                // Roda o container mapeando a porta externa 8081 para a interna 80
                sh 'docker run -d -p 8081:80 --name site-social site-social'
                echo 'Site atualizado e publicado com sucesso na porta 8081! 🚀'
            }
        }
    }
}
