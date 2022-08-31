# Acesso Remoto SSH com (Host Only) no Virtual Box:

O primeiro passo é ativar ou criar uma interface no computador para estabelecer a comunicação entre o Host e a VM;
Para isso, devemos fazer o login na VM;

```shell
- Usuário da VM: administrador
- Senha da VM: adminifal
```

* Clique em ``Arquivo``->``Host Network Manager``;

FIGURA AQUI

## Configurando o servidor DHCP no adaptador VBoxNet0


* Clicar na aba ``Servidor DHCP``

FIGURA AQUI

* Verificar a configuração das interfaces usando o ``Terminal``;

```shell
ifconfig -a       # verifica se existe a interface ``vboxnet0``
```

## Adicionando um adaptador (HostOnly) em uma VM

* Para atribuir acesso a uma VM via rede pelo ``Terminal`` do host devemos adicionar um novo adapatador de rede à VM.

FIGURA AQUI

## Ativando as configurações da Interface na VM para o servidor DHCP
