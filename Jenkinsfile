pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
checkPreviousEnvironment()
}
}
    }
}

def checkPreviousEnvironment(){
    env='QA'
  datas = readYaml file: '/Users/harinder/Documents/sharedlibraryv2/config.yml'
  
 indexOfPreviousEnvironement=null
  for(int i=0;i<datas.size();i++){
     
      if(datas.get(i)[env]){
        indexOfPreviousEnvironement = i-1
        if(i!=0){
          
          println "list of previous environemtns - " + datas.get(indexOfPreviousEnvironement).values().flatten()
          println "continue with deployment"
          break;
      }else{
         
          println "Continue with deploymebnt"
          break;
      }
     
     }


      }  

       if (indexOfPreviousEnvironement == null){

        println "environment not found"
      }  


}
