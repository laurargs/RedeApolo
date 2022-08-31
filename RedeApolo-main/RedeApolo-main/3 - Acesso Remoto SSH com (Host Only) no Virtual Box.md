# Acesso Remoto SSH com (Host Only) no Virtual Box:

O primeiro passo é ativar ou criar uma interface no computador para estabelecer a comunicação entre o Host e a VM;
Para isso, devemos fazer o login na VM;

```shell
- Usuário da VM: administrador
- Senha da VM: adminifal
```

* Clique em ``Arquivo``->``Host Network Manager``;

FIGURA AQUI

### Configurando o servidor DHCP no adaptador VBoxNet0


* Clicar na aba ``Servidor DHCP``

FIGURA AQUI

* Verificar a configuração das interfaces usando o ``Terminal``;

```shell
ifconfig -a       # verificar se existe a interface ``vboxnet0``
```

### Adicionando um adaptador (HostOnly) em uma VM

* Para atribuir acesso a uma VM via rede pelo ``Terminal`` do host devemos adicionar um novo adapatador de rede à VM.

FIGURA AQUI

### Ativando as configurações da Interface na VM para o servidor DHCP

* Verificar as interfaces com ``ifconfig -a``

```shell
ifconfig -a       # verificar se existe a interface ``enp0s8``
```

* Configurando as interfaces no netplan e ativando o DHCP para o Adaptador 2 (enp0s8)

```shell
sudo nano /etc/netplan/01-netcfg.yaml
```

FIGURA AQUI

* Ativando as configurações e verificando se foi atribuido o IP na nova interface de rede:

```shell
sudo netplan apply
ifconfig -a
```

FIGURA AQUI

[VOLTAR AO PASSO ANTERIOR](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/2%20-%20Roteiro%20SSH-Server.md)

[SEGUIR PARA O PRÓXIMO PASSO](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/4%20-%20Configura%C3%A7%C3%A3o%20est%C3%A1tica%20de%20Nomes.md)
