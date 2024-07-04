pipeline {
 agent {
 label "jenkins-node01"
 }

 stages {
   stage('Checkout') {
     steps {
       git branch: 'main', 
       url: 'https://github.com/ruruoh21/mywebapp'
 }
 }
 stage('Build') {
 steps {
 sh 'mvn clean package'
 }
 }
 stage('Deploy') {
 steps {
 deploy adapters: [tomcat9(credentialsId: 'tomcat-manager', 
 path: '', url: 'http://192.168.56.102:8080/')], 
 contextPath: null, war: 'target/hello-world.war'
 }
 }
 }
}