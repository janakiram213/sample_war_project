node {
   stage ('SCM Checkout'){
     git 'https://github.com/janakiram213/sample_war_project'
   }
   stage ('Validate'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn validate"
    }
stage ('Compile'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn compile"
    }
stage ('Test'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn test"
    }
stage ('Package'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }

   stage ('deploy to tomcat'){
      sshagent(['tomcat-dev']) {
          sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.86.233:home/ec2-user/apache-tomcat-7.0.94/webapps'
    }
  }
}    
