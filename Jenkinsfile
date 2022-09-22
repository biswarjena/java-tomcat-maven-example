pipeline {
  agent any
  stages {
    stage('Continuous Integration') {
      steps {
        withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {
          bat 'mvn clean'
          bat 'mvn test cobertura:cobertura install'
          cobertura(autoUpdateHealth: true, autoUpdateStability: true, failUnstable: true, classCoverageTargets: '/target/site/cobertura/*.xml', coberturaReportFile: '/target/site/cobertura/*.xml')
        }

      }
    }

  }
}