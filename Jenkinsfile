pipeline{
  agent any 
  tools {
    maven "maven"
  }  
  stages {
    stage('git clone'){
      steps{
         git 'https://github.com/olochkabar/mavenwebapp'
      }
    }
    stage('Build'){
      steps{
        sh "mvn clean package"
      }
    }
    stage('docker build'){
      steps{
        script {
          withSonarQubeEnv(credentialsId: 'newsonar') {
            sh "mvn sonar:sonar"
          }
        }
      }
    }
    /*stage('docker build'){
      steps{
        script {
          withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
            sh "docker build -t teslar:1 ."
          }
        }
      }
    }
    stage('5uploadNexus'){
      steps{
       withSonarQubeEnv(credentialsId: 'newsonar') {
    // some block
}
      }
    } 
    stage('8deploy2prod'){
      steps{
        deploy adapters: [tomcat8(credentialsId: 'tomcat-credentials', path: '', url: 'http://35.170.249.131:8080/')], contextPath: null, war: 'target/*war'
      }
    }
}
  post{
    always{
      emailext body: '''Hey guys
Please check build status.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    }
    success{
      emailext body: '''Hey guys
Good job build and deployment is successful.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    } 
    failure{
      emailext body: '''Hey guys
Build failed. Please resolve issues.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    }
  } 
  */
}
}
