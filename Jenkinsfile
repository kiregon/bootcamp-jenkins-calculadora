pipeline {
agent any

tools {
maven "maven 3.9.9"
}
stages {
  stage('Build') {
    setps {
       sh 'mvn -B -q package'
    }
}
}
}
