node {
    stage('miseAjour') {
      sh 'sudo apt update'
      sh 'sudo apt install apt-transport-https ca-certificates curl software-properties-common'
      sh 'curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -'
      sh 'sudo apt update'
    }
    stage('installation') {
      sh 'javac Main.java'
    }
    stage('test') {
      sh 'java Main'
   }
}
