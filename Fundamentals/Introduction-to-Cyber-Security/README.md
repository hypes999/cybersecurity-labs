# Introduction to Cyber Security

## Objetivo
Este módulo fornece uma visão geral sobre cibersegurança, incluindo conceitos de **offensive e defensive security**, e explora carreiras na área.

## Conceitos Chave
- **Offensive Security:** Exploração de vulnerabilidades em ambientes seguros para fins educativos (ethical hacking).
- **Defensive Security:** Proteção de sistemas contra ataques, incluindo Threat Intelligence, SOC, DFIR, Malware Analysis, SIEM.
- **Carreiras em Cyber Security:** Ethical hacker, SOC analyst, Forensic analyst, Malware researcher, entre outros.

## Atividades Práticas

### Hack de uma aplicação vulnerável online (ambiente seguro) para experimentar tarefas de um ethical hacker.

_We will use a command-line application called "Gobuster" to brute-force FakeBank's website to find hidden directories and pages. Gobuster will take a list of potential page or directory names and try accessing a website with each of them; if the page exists, it tells you._

_Step 1. Open A Terminal_

_A terminal, also known as the command line, allows us to interact with a computer without using a graphical user interface. On the machine, open the terminal by clicking on the Terminal icon on the right of the screen._

<img width="769" height="379" alt="imagem" src="https://github.com/user-attachments/assets/41878d18-8bac-4f56-919e-6b299354080a" />

_Step 2. Use Gobuster To Find Hidden Website Pages_

_Most companies have an admin portal page, giving their staff access to basic admin controls for day-to-day operations. For a bank, an employee might need to transfer money to and from client accounts. Due to human error or negligence, there may be instances when these pages are not made private, allowing attackers to find hidden pages that show or give access to admin controls or sensitive data._

_To begin, type the following command into the terminal to find potentially hidden pages on FakeBank's website using Gobuster (a command-line security application)._

_**gobuster -u http://fakebank.thm -w wordlist.txt dir**_

_The command will run and show you an output similar to this:_

<img width="731" height="596" alt="imagem" src="https://github.com/user-attachments/assets/2947765d-3495-4563-9430-3eaad6f44da9" />

_In the command above, -u is used to state the website we're scanning, -w takes a list of words to iterate through to find hidden pages._

_You will see that Gobuster scans the website with each word in the list, finding pages that exist on the site. Gobuster will have told you the pages in the list of page/directory names (indicated by Status: 200)._

_Step 3. Hack The Bank_

_You should have found a secret bank transfer page that allows you to transfer money between bank accounts (/bank-transfer). Type the hidden page into the FakeBank website using the browser's address bar._

_From this page, an attacker has authorized access and can steal money from any bank account. As an ethical hacker, you would (with permission) find vulnerabilities in their application and report them to the bank to fix them before a hacker exploits them._

_Your mission is to transfer $2000 from bank account 2276 to your account (account number 8881). If your transfer was successful, you should now be able to see your new balance reflected on your account page._

_Go there now and confirm you got the money! (You may need to hit Refresh for the changes to appear)_

<img width="778" height="725" alt="imagem" src="https://github.com/user-attachments/assets/ab35ebc8-e3c5-42d1-a059-b711c5a2132c" />

<img width="662" height="618" alt="imagem" src="https://github.com/user-attachments/assets/2e0331cb-67e6-457d-a558-92cc966458cb" />

<img width="698" height="565" alt="imagem" src="https://github.com/user-attachments/assets/8d515411-ce1f-425e-b171-7ad081c4a7eb" />

- Simulação de defesa de um sistema contra um ataque cibernético.
- Análise de logs e identificação de ameaças.

## Comandos / Ferramentas
- Ferramentas básicas utilizadas podem incluir: navegadores para testes web, SIEM simulators, e utilitários de análise de logs.

## Conhecimento adquirido
- Diferença entre **offensive** e **defensive** security.
- Importância de ambientes legais e controlados para prática de hacking.
- Introdução às principais carreiras e responsabilidades na cibersegurança.
