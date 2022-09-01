# Acesso Remoto SSH com (Host Only) no Virtual Box:

O primeiro passo é ativar ou criar uma interface no computador para estabelecer a comunicação entre o Host e a VM;
Para isso, devemos fazer o login na VM;

```shell
- Usuário da VM: administrador
- Senha da VM: adminifal
```

Figura 1: Configuração do servidor DHCP.

![WhatsApp Image 2022-08-31 at 10 45 58](https://user-images.githubusercontent.com/103062837/187696296-59073236-b113-4045-83b7-f1c27414d1e0.jpeg)
* Clique em ``Arquivo``->``Host Network Manager``;
* Clicar na aba ``Servidor DHCP``

### Configurando o servidor DHCP no adaptador VBoxNet0


Figura 2: Configuração do servidor DHCP, ativando o adaptador 2.

![img hostonly](https://user-images.githubusercontent.com/103062837/187699980-e3916248-ad4a-49ae-b9c2-0c001e56c284.jpeg)


* Verificar a configuração das interfaces usando o ``Terminal``;

```shell
ifconfig -a       # verificar se existe a interface ``vboxnet0``
```

### Adicionando um adaptador (HostOnly) em uma VM

* Para atribuir acesso a uma VM via rede pelo ``Terminal`` do host devemos adicionar um novo adapatador de rede à VM.

### Ativando as configurações da Interface na VM para o servidor DHCP

* Verificar as interfaces com ``ifconfig -a``

```shell
ifconfig -a       # verificar se existe a interface ``enp0s8``
```

* Configurando as interfaces no netplan e ativando o DHCP para o Adaptador 2 (enp0s8)

```shell
sudo nano /etc/netplan/01-netcfg.yaml
```
Figura 3: Verificação da interface.

![3c4dfc91-8b2a-420a-ab27-29d7e8fad921 (2)](https://user-images.githubusercontent.com/103062837/187697733-5bcb92b5-012f-445b-8e6b-7695b6b2e64b.jpeg)



* Ativando as configurações e verificando se foi atribuido o IP na nova interface de rede:

```shell
sudo netplan apply
ifconfig -a
```
Figura 4: Verificando se foi atribuido o IP na nova interface de rede.

![ef12f4ee-07f1-4279-85e8-762290f7a044](https://user-images.githubusercontent.com/103062837/187697894-ffc93842-33f0-489b-8de8-64c29edc9178.jpeg)


[VOLTAR AO PASSO ANTERIOR](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/2%20-%20Roteiro%20SSH-Server.md)

[SEGUIR PARA O PRÓXIMO PASSO](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/4%20-%20Configura%C3%A7%C3%A3o%20est%C3%A1tica%20de%20Nomes.md)
