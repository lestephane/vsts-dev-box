Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", inline: <<-SHELL
    curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
    mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
    sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
    curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
    apt-get update
    apt-get install -y libgtk2.0-0 libxss1 libasound2 # vscode requirements 
    apt-get install -y code nodejs # build-essential
    npm i -g tfx-cli
  SHELL
end
