pipeline {
        agent any

        parameters {
                  choice choices: ['UAT', 'DEV'], name: 'ENV'
                   }

        stages {
             stage('Checkout') {
                 steps {
                        checkout scm 
                       }
                               }
             stage('Build') {
                 steps {
                         sh '/home/remote/Documents/software/apache-maven-3.9.6/bin/mvn install'
                       }
                            }
             stage('Deploy') {
                 steps {
                     script {
                              if ( ENV == 'UAT' ) then {
        	sh 'cp target/conditionparameter.war /home/remote/Documents/software/apache-tomcat-9.0.86/webapps'
        	echo "deployment has been done on UAT!"
                                                       }
                              else ( ENV == 'DEV' ) then {
    		sh 'cp target/conditionparameter.war /home/remote/Documents/software/apache-tomcat-9.0.86/webapps'
    		echo "deployment has been done on DEV!"
			                                 }
                              fi
                             }
                        }
                               }
                 }
         }

                          

