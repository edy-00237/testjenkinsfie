node {
    stage('miseAjour') {
      sh 'sudo apt update'
      sh 'sudo apt install apt-transport-https ca-certificates curl software-properties-common'
      sh 'curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg'
      sh 'echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null'
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
