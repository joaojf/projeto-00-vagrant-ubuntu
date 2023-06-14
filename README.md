# Projeto 00 - Vagrant-Ubuntu

Este é um projeto que visa criar uma máquina virtual utilizando o Vagrant com o sistema operacional Ubuntu 20.04. A máquina virtual será configurada com uma placa de rede em modo bridge e terá as seguintes especificações:

- Nome da máquina: Ubuntu 20.04
- Memória RAM: 1GB
- CPU: 1

## Pré-requisitos

Antes de começar, certifique-se de que o seguinte software esteja instalado em seu sistema:

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Configuração

Siga as etapas abaixo para configurar e iniciar a máquina virtual:

1. Clone o repositório do projeto para o seu ambiente local:

   ```shell
   git clone https://github.com/joaojf/vagrant-ubuntu.git

2. Acesse o diretório do projeto:
   ```shell
   cd projeto-00-vagrant-ubuntu

3. Abra o arquivo Vagrantfile em um editor de texto de sua preferência.
4. Defina o nome da máquina virtual, memória RAM e CPU conforme suas preferências:
   ```shell
   Vagrant.configure("2") do |config|
     config.vm.define "nome_da_maquina" do |machine|
       machine.vm.box = "ubuntu/focal64"
       machine.vm.network "public_network", bridge: "nome_da_interface_de_rede"
       machine.vm.provider "virtualbox" do |vb|
         vb.memory = "1024"
         vb.cpus = "1"
       end
     end
   end
Substitua `"nome_da_maquina"` pelo nome que deseja dar à sua máquina virtual.

Opção adicional `bridge: "nome_da_interface_de_rede"`

Substitua `"nome_da_interface_de_rede"` pelo nome da interface de rede em modo bridge que você deseja usar. Para descobrir o nome da interface, execute o comando `ifconfig` ou `ip` a no seu terminal.

Caso queira aumentar ou diminuir a quantidade de memória RAM ou o número de CPUs, modifique as linhas `vb.memory = "1024"` e `vb.cpus = "1"`, respectivamente.

Salve as alterações no arquivo Vagrantfile.

Inicie a máquina virtual:
  ```shell
   vagrant up
  ```

Agora a máquina virtual será criada e inicializada de acordo com as configurações fornecidas. Você pode acessar a máquina virtual usando o comando `vagrant ssh`.

## Notas
- Certifique-se de ter privilégios de administrador para executar o Vagrant e o VirtualBox.
- Lembre-se de modificar as configurações de memória RAM, CPU e nome da máquina de acordo com suas necessidades.
- Verifique se possui uma conexão de rede adequada para usar o modo bridge.

## Contribuição
Contribuições são bem-vindas! Se você encontrar algum problema ou tiver sugestões para melhorar este projeto, sinta-se à vontade para abrir uma issue ou enviar um pull request.
