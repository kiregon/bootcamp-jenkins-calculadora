pipeline {
   //agent any
   agent { label 'jdk21' }
   
   tools {
      maven "maven 3.9.9"
   }
   parameters {
      string(name: 'PASSWORD', defaultValue:'', description:'Parametro requerido')
   }
   
   stages {
      stage ('ejemplo') {
        steps {
          echo params.PASSWORD
        }
      }
      stage('Build') {
         steps {
            bat 'mvn -B -q package'
            //para linux sh
         }
         post {
           always {
             junit 'target/surefire-reports/*.xml'
           }
         }
      }
   }

/*post {
    failure {
      echo "Cuando falla"
    }
    success {
      echo "Se ejecuto con exito"
    }
    aborted {
      echo "El job se aborto"
    }
    changed {
      echo "Cambió"
    }
    fixed {
      echo "Arreglado"
    }
    always {
      echo "Siempre se ejecuta"
    }
  }*/

   
}
