pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "Iniciando la clonación del repositorio..."
                    try {
                        git branch: 'main', credentialsId: 'github-credentials', url: 'https://github.com/valkarov/Paradigmas-Programacion.git'
                        echo "Clonación del repositorio exitosa."
                    } catch (Exception e) {
                        echo "ERROR: Error al clonar el repositorio: ${e.getMessage()}"
                        error("Failed to clone repository")
                    }
                }
            }
        }
        stage('Execute Commands') {
            steps {
                script {
                    echo "DEBUG: Ejecutando comandos..."
                    try {
                        // aqui los comandos a ejecutar
                        sh 'echo "Comando 1 ejecutado"'
                        sh 'echo "Comando 2 ejecutado"'
                        echo "DEBUG: Comandos ejecutados exitosamente."
                    } catch (Exception e) {
                        echo "ERROR: Error al ejecutar los comandos: ${e.getMessage()}"
                        error("Failed to execute commands")
                    }
                }
            }
        }
    }
}