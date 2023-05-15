node {
    stage('miseAjour') {
      sh 'sudo apt update'
      sh 'sudo apt install apt-transport-https ca-certificates curl software-properties-common'
      sh 'curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -'
      sh 'sudo apt update'
    }
    stage('installationDocker') {
      sh 'sudo apt install docker-ce'
      sh 'sudo systemctl status docker'
      sh 'sudo usermod -aG docker ${USER}'
      sh 'su - ${USER}'
    }
    stage('InstallationDockerCompose') {
      sh 'mkdir -p ~/.docker/cli-plugins/'
      sh 'curl -SL https://github.com/docker/compose/releases/download/v2.3.3/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose'
      sh 'chmod +x ~/.docker/cli-plugins/docker-compose'
   }
    stage('test') {
      sh 'docker --version'
      sh 'docker-compose --version'
   }
}
