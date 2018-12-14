pipeline { 
    agent {
        node { 
            label 'slave-azure' 
        } 
    }
    stages {
      stage ('HelloWorld') {
        agent {
          docker { image 'jtoledog/compiladorjs' }
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
          docker { image 'jtoledog/compiladorjs' }
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
