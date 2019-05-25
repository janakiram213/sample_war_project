node {
   stage ('SCM Checkout'){
     git 'https://github.com/janakiram213/sample_war_project'
   }
   stage ('Compile-Package'){
     //get maven home path
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
    }
}    
