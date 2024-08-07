pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "DEBUG: Iniciando la clonación del repositorio..."
                    try {
                        // Utiliza 'github-credentials' como el ID de las credenciales configuradas
                        git branch: 'main', credentialsId: 'github-credentials', url: 'https://github.com/valkarov/Paradigmas-Programacion.git'
                        echo "DEBUG: Clonación del repositorio exitosa."
                    } catch (Exception e) {
                        echo "ERROR: Error al clonar el repositorio: ${e.getMessage()}"
                        error("Failed to clone repository")
                    }
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    echo "DEBUG: Iniciando la compilación del proyecto..."
                    try {
                        sh 'mvn clean install'
                        echo "DEBUG: Compilación del proyecto exitosa."
                    } catch (Exception e) {
                        echo "ERROR: Error en la compilación del proyecto: ${e.getMessage()}"
                        error("Build failed")
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "DEBUG: Iniciando las pruebas del proyecto..."
                    try {
                        sh 'mvn test'
                        echo "DEBUG: Pruebas del proyecto exitosas."
                    } catch (Exception e) {
                        echo "ERROR: Error en las pruebas del proyecto: ${e.getMessage()}"
                        error("Tests failed")
                    }
                }
            }
        }
    }
}