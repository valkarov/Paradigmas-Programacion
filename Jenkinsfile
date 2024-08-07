pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "DEBUG: Iniciando la clonación del repositorio..."
                    try {
                        git branch: 'main', credentialsId: 'github-credentials', url: 'https://github.com/valkarov/Paradigmas-Programacion.git'
                        echo "DEBUG: Clonación del repositorio exitosa."
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
                        // Coloca aquí los comandos que necesites ejecutar
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