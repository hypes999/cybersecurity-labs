# Networking Concepts — Cyber Security 101 (THM)

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
ifconfig          # ou ip address show

# (Windows)
ipconfig

# Conectar via telnet a porta TCP (se existir alvo)
telnet TARGET_IP PORT
```
