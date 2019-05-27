node {
   stage ('SCM Checkout'){
     git 'https://github.com/janakiram213/sample_war_project'
   }
   stage ('Compile-Package'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }
   stage ('deploy to tomcat'){
      sshagent(['e47a75a5-b427-4353-ae0c-f2adf8957108']) {
           sh= 'StrictHostKeyChecking=no'target/*.war ec2-user@172.31.86.233:/opt/tomcat/webapps'
    }
  }
}    
