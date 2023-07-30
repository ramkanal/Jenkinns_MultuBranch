node('built-in') {
    stage('Download') {
        git 'https://github.com/ramkanal/maven.git'
    }
    stage('Build') {
        sh 'mvn package'
    }
    stage('Deploy in QA') {
        sh 'scp /home/ubuntu/workspace/workspace/slave-pipeline-script-job/webapp/target/webapp.war ubuntu@172.31.12.247:/var/lib/tomcat9/webapps/qaenv.war'
    }
    stage('Tset in QA') {
        sh 'echo "ALL TESTS ARE PASSED!!!!!!!"'
    }
    stage('Deploy in Prod') {
        sh 'scp /home/ubuntu/workspace/workspace/slave-pipeline-script-job/webapp/target/webapp.war  ubuntu@172.31.0.112:/var/lib/tomcat9/webapps/prodenv.war'
    }
}
