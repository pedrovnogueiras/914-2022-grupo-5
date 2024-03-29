# Projeto 2º Bimestre das disciplinas de Infraestrutura e Serviços de Redes (PRIR/SRED e ISRE)

## Criando uma rede ponto a ponto (Uma LAN com 4 VMs):
### Passo 0 - Terminar a prática <a href='https://github.com/diozenio/914-2022-grupo-5/blob/main/Roteiro/CriandoConex%C3%A3oPontoAPonto.md'>Criando Conexão Ponto a Ponto</a>

### Passo 1 - Criando uma Rede ponto a ponto
  
  * Verifique nas configurações das VMs se as NICs estão em modo `Rede interna`
  * Abra os terminais nos PCs 1 e 2 para criar uma rede ponto a ponto entre os dois PCs
  
  > __OBS: Foram criadas 8 máquinas virtuais. No entanto, para esse teste foi estabelecido uma conexão dentro do VirtualBox entre duas máquinas.__


  <p><center> Figura 2: Topologia de Rede Ponto a Ponto usando o VitualBox, com duas VMs com suas NICs em modo Rede Interna</center></p>   
    <img src="figuresBridgeNetwork/BridgeNetwork.png" alt=""
    title="Figura 2: Topologia de Rede" width="500" height="auto" />

  ### Passo 2 - Faça o login nas máquinas:
   * Úsuário da VM: `administrador`
   * Senha da VM: `adminifal`

  ## Configuração estática de endereço IP na interface de rede 
```
Tabela 1: Definições de endereços IPs da Rede 
-----------------------------------------
|     DESCRICAO       |       IP        |
-----------------------------------------
| rede                | 192.168.14.0    |
| máscara             | 255.255.255.240 |
| Gateway             | 192.168.14.28   |
| VM1-PC1-Carolina    | 192.168.14.65   | 
| VM2-PC1-Carolina    | 192.168.14.66   |
| VM1-PC2-Dionísio    | 192.168.14.67   |
| VM2-PC2-Dionísio    | 192.168.14.68   |
| VM1-PC3-Ewerton     | 192.168.14.69   |
| VM2-PC3-Ewerton     | 192.168.14.70   |
| VM1-PC4-Giovana     | 192.168.14.71   |
| VM2-PC4-Giovana     | 192.168.14.72   |
-----------------------------------------
```
### Configure o endereço IP de acordo com as suas informações estabelecidas. 
  * Para configurar o endereço IP, acesse <a href='https://github.com/diozenio/914-2022-grupo-5/blob/main/Roteiro/CriandoConex%C3%A3oPontoAPonto.md'>Criando Conexão Ponto A Ponto</a> e vá em **Configuração estática de endereço IP na interface de rede**.

## Configurando a rede `bridge` do VirtualBox nos PCs e nas VMs
  * Abra as configurações de cada VM e mude sua configuraão para `Placa em modo bridge` e seu nome para `eno1`

Figura: Configuração das NICs como modo `bridge`
  <img src='../Imagens/placa modo bridge.png'>

  ### Teste a conexão entre as VMs com o comando `ping`
    * No exemplo abaixo, utilizamos apenas duas máquinas para fazer o teste.

  <img src='../Imagens/Captura de tela de 2022-08-09 11-16-04.png'>

  * Ping da VM1-PC1-Carolina para VM2-PC1-Carolina
  ```bash
  ping 192.168.14.66  #ctrl + c para finalizar o comando
  ```
  * Ping da VM2-PC1-Carolina para VM1-PC1-Carolina
  ```bash
  ping 192.168.14.65  #ctrl + c para finalizar o comando
  ```

  <img src='../Imagens/Captura de tela de 2022-08-09 11-16-04.png'>
