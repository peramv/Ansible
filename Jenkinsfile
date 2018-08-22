pipeline {
    agent any
    tools{
    maven 'MAVEN-3.5'
    jdk 'JDK1.8.101'
     }
     // using the Timestamper plugin we can add timestamps to the console log
    options {
        timestamps()
   
    } 
    stages {
        stage ('Initialize for Shopizer') {
                steps {
                sh '''
                    echo "This Jenkinsfile for Building Shopizer Project"
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                    echo "JAVA_HOME = ${JAVA_HOME}"
                    '''
                }
            }
        stage ('Build the code using Maven') {
                steps {
                    sh 'mvn clean compile install'
                    }
         }
        stage ('archiveArtifacts for Shopizer'){
            steps {
                archiveArtifacts '**/**/shopizer.war'
            }
        }
   
    }
}//pipeline
