pipeline {
    agent any //jenkins puede elegir cualquier nodo disponible para ejecutar el pipeline

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/tu-usuario/tu-repositorio.git'
            }
        }
        stage('Build') {
            steps {
                // Compila el proyecto usando Maven
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                // Ejecuta las pruebas
                sh 'mvn test'
            }
        }
    }
}