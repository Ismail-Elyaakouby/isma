node {
  try {
    stage('checkout') {
      checkout scm
    }
    stage('prepare') {
      sh "git clean -fdx"
    }
    stage('buikd') {
      echo "buikd..."
      sh 'mvn clean install'
    }
    stage('test') {
         echo "test"
         env.NODE_ENV = "test"
         print "Environment will be : ${env.NODE_ENV}"
         sh 'mvn -B -DskipTests clean install -Dmaven.clean.failOnError=false'
    }
    stage('deploy') {
      //sh "tar -cvzf hello.tar.gz hello.sh"
      echo "deploy"
    }
    stage('Delivery') {
      echo "Delivery"
    }
  } finally {
    stage('cleanup') {
      echo "doing some cleanup..."
    }
  }
}
