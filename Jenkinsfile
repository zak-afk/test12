pipeline {                                              
  agent  any                  
  parameters {
      choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:' to choose the version')
      booleanParam (name: 'executeTests', defaultValue: true, description: '')   }
  stages  {
             stage("build") {
                 steps {
                    echo "build"
                         }
                }
              stage("test") {             
                 when {            # le stage test ne s'execute que si le params.exec est True
                        expression {
                               params.executeTests   # or params.executeTests == true      
                            }
                     }
                 steps {
                    echo "test"
                         }
                }
              stage("deploy") {
                  steps {
                           echo "deploying the app version ${params.VERSION}"
                         }
                }
            }
 }
