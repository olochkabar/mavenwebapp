pipeline{
  agent any 
  tools {
    maven "maven"
    sonar "sonar"
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
    stage('CodeQuality'){
      steps{
       
        sh "mvn sonar:sonar -Dsonar.projectKey=mavenwebapp -Dsonar.host.url=http://35.183.9.222:9000 -Dsonar.login=971937ee857342c83e5fddf00f185190123a6e09"
      }
    }
    /*stage('5uploadNexus'){
      steps{
        sh "mvn deploy"
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
