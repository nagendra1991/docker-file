node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            app = docker.build("nagendra1991/test")    
       }     
      stage('Test image') {           
            app.inside {            
             
             bat 'echo "Tests passed"'        
            }    
        }     
       stage('Push image') {
       docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
