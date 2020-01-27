pipeline {
  agent any

  tools {
    maven "apache-maven-3.6.3"
  }

  stages {
    stage('Build') {
      steps {
        git 'https://github.com/ajlanghorn/dvja.git'
        sh "mvn clean package"
      }
    }
stage('Check dependencies') {
steps {
dependencyCheck additionalArguments: '', odcInstallation: 'Dependency-Check'
dependencyCheckPublisher pattern: ''

}
}
<<<<<<< HEAD
stage('Scan for vulnerabilities') {
    steps {
        sh 'zap-cli quick-scan --self-contained --spider -r http://127.0.0.1 && zap-cli report -o zap-report.html -f html'
    }
}

=======
>>>>>>> parent of 6f35eee... Update Jenkinsfile

    stage('Publish to S3') {
      steps {
        sh "aws s3 cp /var/lib/jenkins/workspace/dvja/target/dvja-1.0-SNAPSHOT.war s3://cicdsecworkshop2-buildartifacts-164g3qkisx5ku/dvja-1.0-SNAPSHOT.war"
      }
    }
    stage('Tidy up') {
      steps {
        cleanWs()
      }
    }
  }
}
