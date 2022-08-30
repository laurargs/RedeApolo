# Criação do ambiente do projeto:

Antes de iniciar a configuração do ambiente de rede é necessário identificar a existência do Softeware VirtualBox, o qual estará contido as máquinas virtuais.
Tendo o VirtualBox no computador o primeiro passo é criar o ambiente onde as MVs estarão.



- Abrir o terminal do computador e logar no usuário redes;


![1e0bbee7-19d0-40f2-898b-bf7a00de19cd](https://user-images.githubusercontent.com/97605797/187445010-6dfd4137-5473-4954-9359-c275732bd387.jpeg)
- Após logar no usuário redes, foi criado um pasta "labredes" e dentro dessa, uma outra com o nome "vmAPOLLO"; 
- Obs: o erro destacado na imagem, ocorreu pelo fato de termos criado as pastas antes dos prints;

### CRIAÇÃO DAS VMs:

Ao abrir o VirtualBox, o primeiro passo é importar a imagem, o arquivo .OVA é um formato de exportação de VM utilizado pelo VirtualBox.
- Na pasta labredes, em images, em original, importar a imagem( seguindo a descrição da figura abaixo);
- Caso não tenha adicionado em seu computador a imagem, [é necessário seguir este passo-a-passo](https://github.com/alaelson/2022-924-notasdeaula/blob/main/Aula.924.2022.06.22.md)
![WhatsApp Image 2022-08-30 at 10 29 16](https://user-images.githubusercontent.com/97605797/187450057-e0371d55-9474-486b-b1a1-0b050f06328e.jpeg)

Após importar a imagem.
- Definir o nome da MV, denominamos de VM7-PC4-GRUPO02( seguindo a descrição da tabela adicionada );
- Definir o local de armazenamento da VM em: 'Pasta padrão para máquinas', adicionamos-a na pasta criada 'vmAPOLLO';
- Gerar novos endereços físicos é fundamental para criar uma máquina diferente da outra. Dessa forma é necessário, em política de endereço MEC, selecionar a opção: gerar novos endereços MEC para todas as placas de rede;
- Depois de clicar na opção 'importar', a máquina será criada.


![Captura de tela de 2022-08-30 10-23-23](https://user-images.githubusercontent.com/97605797/187450003-f2cd1330-616d-4b9a-b2f8-af8490cf3128.png)

[SEGUIR PARA O PRÓXIMO PASSO](https://github.com/laurargs/RedeApolo/blob/main/RedeApolo-main/RedeApolo-main/2%20-%20Roteiro%20SSH-Server.md)
