pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
<<<<<<< HEAD
                // Baixa o código do seu GitHub
=======
                // Baixa a versão mais recente do código do seu GitHub
>>>>>>> 9ddc8a0 (feat: adiciona Dockerfile e atualiza pipeline real do Jenkins)
                checkout scm
            }
        }

<<<<<<< HEAD
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
=======
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
                // Remove o container antigo se ele existir. O '|| true' evita que o pipeline quebre se não houver container rodando
                sh 'docker rm -f site-social || true'
            }
        }

        stage('Subir Novo Container') {
            steps {
                echo 'Iniciando o novo container na porta 8081...'
                // Roda o container em segundo plano (-d), mapeia a porta externa 8081 para a interna 80 e define o nome
                sh 'docker run -d -p 8081:80 --name site-social site-social'
                echo 'Site atualizado e publicado com sucesso na porta 8081! 🚀'
>>>>>>> 9ddc8a0 (feat: adiciona Dockerfile e atualiza pipeline real do Jenkins)
            }
        }
    }
}