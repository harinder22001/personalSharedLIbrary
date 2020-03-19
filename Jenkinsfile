
def  env='asdf'
pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
 

                checkOutput(checkPreviousEnvironment(env))

}
}
    }
}

def checkPreviousEnvironment(env){
   
  datas = readYaml file: '/Users/harinder/Documents/sharedlibraryv2/config.yml'
  
 indexOfPreviousEnvironement=null
  for(int i=0;i<datas.size();i++){
     
      if(datas.get(i)[env]){
        indexOfPreviousEnvironement = i-1
        if(i!=0){
          
          return datas.get(indexOfPreviousEnvironement).values().flatten()
      }else{
         
          return "Not Applicable"
      }
     
     }


      }  

       if (indexOfPreviousEnvironement == null){

        return "Error"
      }  


}

void checkOutput(priviousEnvironment){
  if (priviousEnvironment=="Not Applicable"){

  println "Deployment will continue"

   echo "\033[32m### Deployment will continue in environment ${env}  ###\033[0m"

}else if (priviousEnvironment == "Error"){

   echo "\033[31m[ERROR] :  Environment not found in config file \033[0m"

  }else{

       echo "\033[32m### List of previous environments is: ${priviousEnvironment} ###\033[0m"




  }
}
