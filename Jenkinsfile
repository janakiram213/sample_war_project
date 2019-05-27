node {
   stage ('SCM Checkout'){
     git 'https://github.com/janakiram213/sample_war_project'
   }
   stage ('Validate'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }
stage ('Compile'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }
stage ('Test'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }
stage ('Package'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }

   stage ('deploy to tomcat'){
      sshagent(['e47a75a5-b427-4353-ae0c-f2adf8957108']) {
           sh= 'scp -o StrictHostKeyChecking=no /home/jenkins-slave-01/workspace/deploy_war_file/target/hello-1.0.war ec2-user@172.31.86.233:/opt/tomcat/webapps'
    }
  }
}    
