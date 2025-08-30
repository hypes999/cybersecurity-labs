# Networking Concepts

Este módulo introduz os fundamentos de networking, incluindo os modelos OSI e TCP/IP, endereçamento IP, protocolos de transporte e encapsulação de pacotes. 

## Objetivos
- Compreender o modelo ISO/OSI.
- Entender o modelo TCP/IP e o mapeamento com o OSI.
- Aprender sobre endereços IP, subnets e configuração de rede.
- Diferenças entre TCP e UDP, números de porta.
- Usar ferramentas CLI para conectar a portas TCP abertas.
- Entender encapsulação e o ciclo de vida de um pacote.

## Passo a passo
1. Estudar o modelo **OSI** e suas 7 camadas, do físico (1) ao aplicativo (7).
2. Comparar com o modelo **TCP/IP** (Link, Internet, Transport, Application).
3. Explorar **endereços IPv4** e sub-redes.
4. Entender **portas TCP/UDP** e como se conectar a portas abertas via terminal.
5. Estudar **encapsulação**: como os dados transitam através das camadas.
6. Seguir a trajetória de um pacote desde o navegador até o servidor web.

## Comandos e scripts

```bash
# Ver configuração de rede (Linux)
ifconfig      # ou ip a

# (Windows)
ipconfig  # para mais detalhes ipconfig /all

# Conectar via telnet a porta TCP (se existir alvo)
telnet TARGET_IP PORT
```

## Modelo OSI (7 Camadas)

O modelo OSI é composto por 7 camadas, cada uma com funções específicas:

1. **Camada Física**: Responsável pela transmissão física dos dados, como cabos, conectores e sinais elétricos.
2. **Camada de Enlace de Dados**: Garante a comunicação entre dispositivos na mesma rede local, detectando e corrigindo erros.
3. **Camada de Rede**: Responsável pelo roteamento dos pacotes através de diferentes redes, como no caso do protocolo IP.
4. **Camada de Transporte**: Garante a entrega confiável de dados, podendo usar TCP ou UDP.
5. **Camada de Sessão**: Estabelece, mantém e termina sessões de comunicação entre aplicativos.
6. **Camada de Apresentação**: Converte e traduz dados entre o formato usado pelos aplicativos e o formato de rede (exemplo: compressão, criptografia).
7. **Camada de Aplicação**: A camada mais próxima do usuário, onde os aplicativos como HTTP, FTP, SMTP, etc., operam.

## Modelo TCP/IP (4 Camadas)

O modelo TCP/IP é uma versão simplificada do modelo OSI, com 4 camadas:

1. **Camada Link**: Combina a camada física e a camada de enlace de dados do modelo OSI. Cuida da transmissão de dados através de um meio físico.
2. **Camada Internet**: Equivalente à camada de rede do modelo OSI, ela lida com roteamento e endereçamento de pacotes (exemplo: IP).
3. **Camada de Transporte**: Responsável pelo controle de fluxo e entrega dos pacotes de dados. A comunicação pode ser via TCP ou UDP.
4. **Camada de Aplicação**: Lida com os protocolos de comunicação entre os aplicativos, como HTTP, FTP, etc.

### HTTP no Modelo TCP/IP

- O **HTTP** (Hypertext Transfer Protocol) pertence à camada **Aplicação** do modelo TCP/IP.
- Ele cobre **três camadas do modelo OSI**: **Sessão**, **Apresentação** e **Aplicação**.
  - **Sessão**: Controla o início, manutenção e fim das sessões de comunicação.
  - **Apresentação**: Responsável pela conversão de dados, como codificação de texto e criptografia.
  - **Aplicação**: Onde os protocolos HTTP, FTP, etc., operam.

### Endereços IP e Sub-redes

- **IPv4**: Um endereço de 32 bits (4 octetos), utilizado para identificar dispositivos em uma rede.
- **Endereços IP Públicos vs Privados**:
  - **Públicos**: São usados na internet, únicos globalmente.
  - **Privados**: Usados em redes locais (LANs), não roteados na internet.
- **Máscara de Sub-rede**: Define quais partes do endereço IP são para a rede e quais são para os hosts (exemplo: `255.255.255.0`).

### TCP vs UDP

- **UDP (User Datagram Protocol)**:
  - Protocolo leve, **sem confirmação de entrega**.
  - Ideal para **velocidade**, como streaming e jogos online.
  - Não garante a ordem ou a integridade dos dados.
  
- **TCP (Transmission Control Protocol)**:
  - **Orientado à conexão**, confiável.
  - Estabelece uma conexão via **three-way handshake**: 
    1. **SYN**: Solicitação de conexão.
    2. **SYN-ACK**: Confirmação da solicitação.
    3. **ACK**: Estabelecimento da conexão.
  - Garante a entrega de dados na ordem correta.

### Encapsulação

- Cada camada do modelo OSI e TCP/IP **acrescenta um cabeçalho (header)** ou **trailer** aos pacotes de dados, formando **frames** na camada de enlace.
- O processo de encapsulação é responsável pela transformação dos dados em pacotes, que são transmitidos entre os dispositivos.
  
## Vida de um Pacote

1. **Início na Aplicação**: Um pacote de dados é gerado por um aplicativo, como HTTP.
2. **Handshake TCP**: Caso esteja utilizando TCP, o pacote passa pelo processo de **three-way handshake** (SYN, SYN-ACK, ACK).
3. **Encapsulação IP**: O pacote recebe um cabeçalho IP, com informações de endereçamento de rede.
4. **Encapsulação de Enlace de Dados**: O pacote é encapsulado com cabeçalhos de enlace (ex: Ethernet).
5. **Roteador**: O pacote chega a um roteador, que o encaminha para o destino.
6. **Servidor**: O pacote chega ao servidor, que processa a solicitação e envia uma resposta.
7. **Resposta**: A resposta é devolvida ao cliente, passando pelos mesmos processos no caminho de volta.

## Imagens / Diagramas

Para ilustrar o fluxo de pacotes e o modelo de camadas, seria interessante incluir diagramas. Podemos gerar diagramas explicativos usando ferramentas externas.

Se precisar de algum diagrama ou imagem, posso ajudar a gerar com uma descrição específica.

