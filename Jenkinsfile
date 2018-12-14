pipeline { 
    stages {
      stage ('HelloWorld') {
        agent {
          docker { image 'sergioguti/prueba' }
        }
        steps {
              sh "echo 'Hello World'"
            sh "env"
        }
        post {
          success {
            echo 'Se ha saludado correctamente'
          }
          failure {
            echo 'Se ha producido error en el saludo :D'
          }
      }
      }

      stage ('NPM compile') {
        agent {
          docker { image 'sergioguti/prueba' }
        }
        steps {
          script {
            libreria.compile 'prueba'
          }
        }
        post {
          success {
            echo 'Se ha descargado el repositorio'
          }
          failure {
            echo 'Se ha producido error en el saludo :D'
          }
      }
      }
      
    }
}
