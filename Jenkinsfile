pipeline {

   agent any

            stages {

      stage('Git Checkout') {

         steps {

            git 'https://github.com/nikhilbandagi/mvn_sonar.git'

                        }

            }
           
            
            stage ('Build') {

                        steps {

                                   sh '/opt/apache-maven-3.8.3/bin/mvn clean sonar:sonar -Dmaven.test.skip=true'

                        }

            }

            stage('Artifact-Deployment') {

         steps {

            sh ' /usr/share/maven clean deploy -Dmaven.test.skip=true'

            }
            }
            stage('Release') {

         steps {

           sh 'export JENKINS_NODE_COOKIE=dontkillme ;nohup java -jar $WORKSPACE/target/*.jar &'

                        }

            }


}

}
