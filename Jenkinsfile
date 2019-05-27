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
      sshagent(['tomcat-proj']) {
          sh 'scp -o StrictHostKeyChecking=no target/*.war root@172.31.86.233:/root/apache-tomcat-7.0.94/webapps'
    }
  }
}    
