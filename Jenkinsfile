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
    post {
        success {
            emailext(
                subject: "Pipeline completado con éxito: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                body: """<p>El pipeline <b>${env.JOB_NAME}</b> se completó con éxito en la build <b>${env.BUILD_NUMBER}</b>.</p>
                         <p>Puedes ver más detalles en: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>""",
                to: 'val16flores@gmai.com'
            )
        }
        failure {
            emailext(
                subject: "Pipeline fallido: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                body: """<p>El pipeline <b>${env.JOB_NAME}</b> falló en la build <b>${env.BUILD_NUMBER}</b>.</p>
                         <p>Error: ${currentBuild.result}</p>
                         <p>Puedes ver más detalles en: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>""",
                to: 'val16flores@gmai.com'
            )
        }
    }
}