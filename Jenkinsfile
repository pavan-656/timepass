pipeline {
          agent {
		  label {
		 label "built-in"
					 customWorkspace "/mnt/git"
					 }
					 }
					 environment {
					     PATH = "/mnt/build-tools/apache-maven-3.8.7/bin:$PATH"
					 }
					  stages {
					  
					  stage ('git-clone') {
					  steps {
					  sh "rm -rf *"
					  sh "git clone https://github.com/Shantanumajan6/project.git"
					  }
					  }
					  stage ('maven-install') {
					  
					  steps {
					  dir ('/mnt/git/project') {
					  sh "mvn clean install"
					  }
					  }
					  }
					  
					  
					  stage ('dev-1') {
                     agent{
                           node {
                                    label 'dev1'
                                                  }
                                                  }
                     steps{
					 dir ('/mnt/docky') {
					 sh "sudo docker-compose down"
					 sh " rm -rf *"
					 sh "git clone https://github.com/pavan-656/timepass.git"
					 
                            sh "sudo docker-compose up -d --scale httpd-server=2"
                                                       }
					                                      }
														  }
					  stage ('dev-2') {
                     agent{
                           node {
                                    label 'dev2'
                                                  }
                                                  }
                     steps{
					 dir ('/mnt/docky') {
					 sh "sudo docker-compose down"
					 sh " rm -rf *"
					 sh "git clone https://github.com/pavan-656/timepass.git"
                            sh "sudo docker-compose up -d --scale httpd-server=2"
                                                       }
					                                      }
														  }
														  stage ('qa-1') {
                     agent{
                           node {
                                    label 'qa1'
                                                  }
                                                  }
                     steps{
					 dir ('/mnt/docky') {
					 sh "sudo docker-compose down"
					 sh " rm -rf *"
					 sh "git clone https://github.com/pavan-656/timepass.git"
                            sh "sudo docker-compose up -d --scale httpd-server=2"
                                                       }
					                                      }
														  }
														  
														  stage ('qa-2') {
                     agent{
                           node {
                                    label 'qa2'
                                                  }
                                                  }
                     steps{
					 dir ('/mnt/docky') {
					 sh "sudo docker-compose down"
					 sh " rm -rf *"
					 sh "git clone https://github.com/pavan-656/timepass.git"
                            sh "sudo docker-compose up -d --scale httpd-server=2"
                                                       }
					                                      }
														  }
}
}
					  
					  
					  
					  
					  
					
