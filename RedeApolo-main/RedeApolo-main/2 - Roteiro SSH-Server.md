# Roteiro SSH-Server (VM VirutalBox e Ubuntu-Server):


O primeiro passo é abrir as VMs e logar no usuário administrador;
Após isso, fazemos a configuração estática de endereço IP na interface de rede;

- O Ubuntu utilizará o arquivo YAML para configurar as interfaces, este arquivo está '/etc/netplan'
- para verificar digite:
```shell
ifconfig -a
ls -la /etc/netplan
cat /etc/netplan/01-netcfg.yaml
```
- Após verificar a existência do arquivo netplan;

### EXEMPLO EM UMA DAS VMs

- instale as ferramentas de rede, com o comando:

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
        enp0s3:                              # nome da interface que está sendo configurada. Verifique com o comando 'ifconfig -a'
            addresses: [192.168.24.19/28]    # IP e Máscara do Host.
            gateway4: 192.168.24.30          # IP do Gateway
            dhcp4: false                     # dhcp4 false -> cliente DHCP está desabilitado, logo o utilizará o IP do campo 'addresses'
    version: 2
```

-sigua o exemplo da figura abaixo:
![WhatsApp Image 2022-08-30 at 11 31 37](https://user-images.githubusercontent.com/97605797/187464670-d5f5ce22-6119-4872-818a-ad84e5dc0390.jpeg)

*  Após salvar o arquivo é necessário aplicar as configurações, com o **netplan apply**. Depois veja a configuração das interfaces com ***ifconfig -a***
```bash
$ sudo netplan apply
$ ifconfig -a
```

