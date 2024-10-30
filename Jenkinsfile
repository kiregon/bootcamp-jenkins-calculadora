pipeline {
   //agent any
   agent { label 'jdk21' }
   
   tools {
      maven "maven 3.9.9"
   }
   parameters {
      password(name: 'PASSWORD', defaultValue:'hola', description:'Parametro requerido')
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
}
