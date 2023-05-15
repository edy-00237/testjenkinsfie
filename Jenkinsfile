node {
    stage('installationDocker') {
      sh 'sudo usermod -aG docker ${USER}'
      sh 'sudo newgrp docker'
    }
    stage('InstallationDockerCompose') {
      sh 'mkdir -p ~/.docker/cli-plugins/'
      sh 'curl -SL https://github.com/docker/compose/releases/download/v2.3.3/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose'
      sh 'sudo chmod +x /usr/local/bin/docker-compose'
   }
    stage('test') {
      sh 'docker --version'
      sh 'docker-compose --version'
   }
}
