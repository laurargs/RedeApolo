# PROJETO E INFRAESTRUTURA DE REDES - GRUPO 2  - 924

                               Tabela 1: Responsáveis por máquina e Designação dos respectivos endereços IPs 

                               -------------------------------------------------------------------------------
                              |                    Responsável                      | Máquina |      IP       |
                              |-----------------------------------------------------|---------|---------------|
                              | Laura Rafaelly Guimarães Silva                      | VM1-PC1 | 192.168.24.17 |
                              |                                                     | VM2-PC1 | 192.168.24.18 |
                              | Jocineide Bruno dos Santos                          | VM1-PC2 | 192.168.24.19 |
                              |                                                     | VM2-PC2 | 192.168.24.20 |
                              | Rayane Araújo de Albuquerque                        | VM1-PC3 | 192.168.24.21 |
                              |                                                     | VM2-PC3 | 192.168.24.22 |
                              | Kauan Nogueira de Amorim                            | VM1-PC4 | 192.168.24.23 |
                              |                                                     | VM2-PC4 | 192.168.24.24 |
                               -------------------------------------------------------------------------------

## Configuração do serviço de nomes estáticos

```
        Tabela 2: Definições de endereços IPs da Rede e Nomes de Hosts
        ---------------------------------------------------------------------------------------------------------------------------
        |  DESCRICAO  |  IP               |   hostname        |          FQDN                 |     aliase       | Gateway        |
        ---------------------------------------------------------------------------------------------------------------------------
        | VM1-PC1     | 192.168.24.17     |   srv-vm1-pc1     | ravena.grupo2-924.ifalara.net |       vogal      | 192.168.24.30  |
        | VM2-PC1     | 192.168.24.18     |   srv-vm2-pc1     | ravena.grupo2-924.ifalara.net |       vogale     |                |
        | VM3-PC2     | 192.168.24.19     |   srv-vm3-pc2     | teresa.grupo2-924.ifalara.net |       www        |                |
        | VM4-PC2     | 192.168.24.20     |   srv-vm4-pc2     | teresa.grupo2-924.ifalara.net |       henri      |                |
        | VM5-PC3     | 192.168.24.21     |   srv-vm5-pc3     | hardin.grupo2-924.ifalara.net |       prefeito   |                |
        | VM6-PC3     | 192.168.24.22     |   srv-vm6-pc3     | hardin.grupo2-924.ifalara.net |       vereador   |                |
        | VM7-PC4     | 192.168.24.23     |   srv-vm7-pc4     | otelo. grupo2-924.ifalara.net |       suredes    |                |
        | VM8-PC4     | 192.168.24.24     |   srv-vm8-pc4     | otelo. grupo2-924.ifalara.net |       pm         |                |
        ---------------------------------------------------------------------------------------------------------------------------

        ```

```
                                           Tabela 3: PC's físicos reservados para cada máquina
                                                    -------------------------------
                                                    |  DESCRICAO  |   PC FÍSICO   |
                                                    -------------------------------
                                                    |     PC1     | LAB 1 - PC 01 |
                                                    |     PC2     | LAB 1 - PC 12 | 
                                                    |     PC3     | LAB 1 - PC 08 |
                                                    |     PC4     | LAB 1 - PC 14 |
                                                    -------------------------------
```
