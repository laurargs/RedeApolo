# Roteiro SSH-Server (VM VirutalBox e Ubuntu-Server):


O primeiro passo é abrir as VMs e logar no usuário administrador;

Após isso, fazemos a configuração estática de endereço IP na interface de rede;

- O Ubuntu utilizará o arquivo YAML para configurar as interfaces, este arquivo está '/etc/netplan'
- Para verificar, digite:
```shell
ifconfig -a
ls -la /etc/netplan
cat /etc/netplan/01-netcfg.yaml
```
- Após verificar a existência do arquivo netplan;

### EXEMPLO EM UMA DAS VMs

- Instale as ferramentas de rede, com o comando:

```bash
$ sudo apt install net-tools -y
```
*  Edite o arquivo  ***01-netcfg.yaml***, use o comando:

```bash
$ sudo nano /etc/netplan/01-netcfg.yaml
```
*  Agora editaremos o arquivo seguindo a descrição da [Tabela](https://github.com/laurargs/RedeApolo/blob/main/Tabela.md) adicionada.
```
network:
    ethernets:
        enp0s3:                           # nome da interface que está sendo configurada. Verifique com o comando 'ifconfig -a'
            addresses: [192.168.24.19/28]    # IP e Máscara do Host.
            gateway4: 192.168.24.30          # IP do Gateway
            dhcp4: false                  # dhcp4 false -> cliente DHCP está desabilitado, logo o utilizará o IP do campo 'addresses'
    version: 2
```

-Siga o exemplo da figura abaixo:

Figura 1: 

![WhatsApp Image 2022-08-30 at 11 31 37](https://user-images.githubusercontent.com/97605797/187464670-d5f5ce22-6119-4872-818a-ad84e5dc0390.jpeg)

*  Após salvar o arquivo é necessário aplicar as configurações, com o **netplan apply**. Depois veja a configuração das interfaces com ***ifconfig -a***
```bash
$ sudo netplan apply
$ ifconfig -a
```

### Atribuir nomes aos servidores hostname:

O próximo passo é difinir os hostnames aos servidores, sendo assim, deve-se seguir os hostnames atribuidos na [Tabela](https://github.com/laurargs/RedeApolo/blob/main/Tabela.md) adicionada.
- deve-se seguir o formato: ``sudo hostnamectl set-hostname <hostname>``

* Exemplo: na VM1-PC1 executar o seguinte comando:
```shell
sudo hostnamectl set-hostname srv-vm1-pc1
```

- Fazer o mesmo nas outras VMs, seguindo as definições de nomes da [Tabela](https://github.com/laurargs/RedeApolo/blob/main/Tabela.md) adicionada.

### Instale o SSH Server

Agora deve-se instalar o protocolo SSH, seguindo o comando abaixo.

```shell
systemctl status ssh
sudo apt-get install openssh-server
systemctl status ssh
```

### Verifique o status das portas do sistema
```
netstat -an | grep LISTEN.  #verifique as conexões TCP na porta 22 se está como LINSTENING
```

### Firewall 
* Para garantir o funcioamento correto do controle de acesso devemos configurar o firewall para permitir conexões remota via protocolo SSH, na porta 22.
 
```shell
sudo ufw status
sudo ufw allow ssh.    # ativa o ssh no firewall UFW do ubuntu.
sudo ufw status
```
    
* Para ativar o firewall:
```shell 
sudo ufw enable
```
[VOLTAR AO PASSO ANTERIOR](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/1%20-%20cria%C3%A7%C3%A3o%20do%20ambiente.md)

[SEGUIR PARA O PRÓXIMO PASSO](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/3%20-%20Acesso%20Remoto%20SSH%20com%20(Host%20Only)%20no%20Virtual%20Box.md)
