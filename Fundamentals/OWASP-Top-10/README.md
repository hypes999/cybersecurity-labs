# OWASP Top 10

Este módulo apresenta as top 10 vulnerabilidades de aplicações web segundo o OWASP, com exploração prática de cada uma.  

## Objetivos

- Identificar cada vulnerabilidade da lista OWASP Top 10 (2021/mais recente).  
- Praticar exploração de falhas web como Injections, Broken Auth, XSS, etc.  
- Aprender comandos/ferramentas usadas para detetar e explorar essas falhas.  
- Refletir sobre mitigação e boas práticas de segurança web.

## Passo a passo

1. Fazer o reconhecimento do ambiente disponibilizado no TryHackMe.  
2. Explorar cada vulnerabilidade conforme o módulo:  
   - Injection  
   - Broken Authentication  
   - Sensitive Data Exposure  
   - XML External Entity  
   - Broken Access Control  
   - Security Misconfiguration  
   - Cross-site Scripting  
   - Insecure Deserialization  
   - Components with Known Vulnerabilities  
   - Insufficient Logging & Monitoring  
3. Para vulnerabilidades práticas (challenges), aplicar exploração manual + usar ferramentas como Burp Suite, navegador, SQLite, etc.  
4. Capturar evidências (screenshots / registros de comando).  
5. Documentar cada falha com: o que fizeste, que comandos ou payloads usaste, e o que aprendeste e como prevenir.

## Comandos e scripts usados

```bash
# Exemplos de exploração de vulnerabilidades

# Listar arquivos no ambiente Linux
ls -la

# Verificar utilizadores
whoami
id

# Aceder a um diretório público /assets
curl http://<MACHINE_IP>/assets/

# Interagir com DB SQLite
sqlite3 webapp.db
.tables
SELECT username, password FROM users WHERE username='admin';

# Exploração de comando injetado via navegador / formulário
# Exemplo de comando injection
$(ls)
$(cat /etc/passwd)

# Usar Burp Suite / Intruder para fuzz de parametros
# Usar ferramenta de cracking de hash externo se aplicável  
```

## Imagens

<p align="center">
  <img src="https://github.com/user-attachments/assets/c3a15b22-2a41-4684-9ec6-a26c1e4efe16" width="600"/>
  <img src="https://github.com/user-attachments/assets/fb0601db-5b81-475f-a3a3-1f66fffc3ba8" width="600"/>
  <img src="https://github.com/user-attachments/assets/8dee56ed-24b5-4df2-8275-1b76a9b48123" width="600"/>
  <img src="https://github.com/user-attachments/assets/dbeedbb6-ca82-4a36-be62-45b3453e5b9b" width="600"/>
  <img src="https://github.com/user-attachments/assets/3e0e431d-38a0-4dd7-84a5-943fa07c39ec" width="600"/>
</p>

---

### 5.1 What strange text file is in the website root directory?  
**Answer:** `drpepper.txt`  

<p align="center">
  <img src="https://github.com/user-attachments/assets/ec433642-a85b-42e2-bced-874781f0fd22" width="600"/>
</p>

---

### 5.2 How many non-root/non-service/non-daemon users are there?  
**Answer:** `0`  

<p align="center">
  <img src="https://github.com/user-attachments/assets/47939d55-ee00-4b30-a245-697b2c69e57e" width="600"/>
</p>

---

### 5.3 What user is this app running as?  
**Answer:** `www-data`  

---

### 5.4 What is the user's shell set as?  
**Answer:** `/usr/sbin/nologin`  

<p align="center">
  <img src="https://github.com/user-attachments/assets/9e9c0cf5-8179-429b-bbe5-55cdb7c404af" width="600"/>
</p>

---

### 5.5 What version of Ubuntu is running?  
**Answer:** `18.04.4`  

<p align="center">
  <img src="https://github.com/user-attachments/assets/034855c2-7fdf-4722-b8cc-1dfaf10c71cd" width="600"/>
</p>

---

### 5.6 Print out the MOTD. What favorite beverage is shown?  
**Answer:** `DR PEPPER`  

<p align="center">
  <img src="https://github.com/user-attachments/assets/535e43af-700e-463f-bea5-2fc91d34834e" width="600"/>
</p>

## 7. Flags (user accounts)

### 7.1 What is the flag that you found in darren's account?  
**Answer:** `fe86079416a21a3c99937fea8874b667`

<p align="center">
  <img src="https://github.com/user-attachments/assets/00a13d4b-5999-4de6-8468-8f94d650b4bd" width="800" alt="flag darren"/>
</p>

---

### 7.3 What is the flag that you found in arthur's account?  
**Answer:** `d9ac0f7db4fda460ac3edeb75d75e16e`

<p align="center">
  <img src="https://github.com/user-attachments/assets/1655a312-f371-4c76-bc70-1893312097fe" width="800" alt="flag arthur"/>
</p>

---

## 11. Sensitive files & admin access

### 11.1 What is the name of the mentioned directory?  
**Answer:** `/assets`

<p align="center">
  <img src="https://github.com/user-attachments/assets/174926bc-9b4e-487e-89b1-cb122deb0485" width="800" alt="/assets listing 1"/>
  <br><br>
  <img src="https://github.com/user-attachments/assets/21651ae7-6b8a-48e1-ae30-2626a64464ec" width="800" alt="/assets listing 2"/>
</p>

---

### 11.2 Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data?  
**Answer:** `webapp.db`

<p align="center">
  <img src="https://github.com/user-attachments/assets/a99396bd-799d-4d3a-a0d9-64cf52ea30cd" width="800" alt="webapp.db"/>
</p>

---

### 11.3 Use the supporting material to access the sensitive data. What is the password hash of the admin user?  
**Answer:** `6eea9b7ef19179a06954edd0f6c05ceb`

*(hash extracted from webapp.db — document the exact SQL query you used in the lab notes)*

---

### 11.4 Crack the hash. What is the admin's plaintext password?  
**Answer:** `qwertyuiop`

<p align="center">
  <img src="https://github.com/user-attachments/assets/dfc4f68f-1644-487f-951d-c3a59cc14760" width="800" alt="hash cracked"/>
</p>

---

### 11.5 Login as the admin. What is the flag?  
**Answer:** `THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}`

<p align="center">
  <img src="https://github.com/user-attachments/assets/d8a9a481-a05b-496b-9ff7-d59c1db84486" width="800" alt="admin flag"/>
</p>

---

### 18.2 Deploy the machine and go to http://MACHINE_IP — Login with the username being noot and the password test1234.
<p align="center">
   <img width="775" height="104" alt="imagem" src="https://github.com/user-attachments/assets/45997b6e-940f-4a6e-8417-62aa8a6041dd" />
</p>

### 18.3 Look at other users notes. What is the flag?
**Answer:** `flag{fivefourthree}`
<p align="center">
   <img width="781" height="94" alt="imagem" src="https://github.com/user-attachments/assets/fecb1a50-560e-4b83-9d85-f38bd7c867b5" />
</p>

---

### 19.1 Deploy the VM
<p align="center">
   <img width="1636" height="328" alt="imagem" src="https://github.com/user-attachments/assets/e9aa4c7c-48c5-41da-adc2-d1a8782810d3" />
</p>

### 19.2 Hack into the webapp, and find the flag!
**Answer:** `thm{4b9513968fd564a87b28aa1f9d672e17}`
<p align="center">   
   <img width="1498" height="481" alt="imagem" src="https://github.com/user-attachments/assets/69cb69cc-904b-4246-ba0f-5b4fdb7151de" />
</p>

---

### 20.1 Deploy the VM
<p align="center">   
   <img width="1660" height="775" alt="imagem" src="https://github.com/user-attachments/assets/6816b9e2-4fbd-4f1f-9a7f-0d9133a6accf" />
</p>

### 20.2 Navigate to http://MACHINE_IP/ in your browser and click on the “Reflected XSS” tab on the navbar; craft a reflected XSS payload that will cause a popup saying “Hello”.
**Answer:** `ThereIsMoreToXSSThanYouThink`
<p align="center">   
   <img width="1009" height="540" alt="imagem" src="https://github.com/user-attachments/assets/22b7ff19-934a-424b-bba1-f824a11eae63" />
</p>

### 20.3 On the same reflective page, craft a reflected XSS payload that will cause a popup with your machines IP address.
**Answer:** `ReflectiveXss4TheWin`
<p align="center">   
   <img width="1502" height="670" alt="imagem" src="https://github.com/user-attachments/assets/5eaf6399-ff25-41d1-b42e-8e8da164bba3" />
</p>

### 20.4 Now navigate to http://MACHINE_IP/ in your browser and click on the “Stored XSS” tab on the navbar; make an account.
<p align="center">   
   <img width="1405" height="379" alt="imagem" src="https://github.com/user-attachments/assets/8196b164-9eea-4a2f-aa51-1783acb981eb" />
   <img width="1394" height="514" alt="imagem" src="https://github.com/user-attachments/assets/19ce8b96-053e-4659-a955-15fd0f15221f" />
</p>

<img width="466" height="185" alt="imagem" src="https://github.com/user-attachments/assets/0be129d6-e136-4f7b-99c8-7174526f1945" />
<img width="644" height="282" alt="imagem" src="https://github.com/user-attachments/assets/e906a4ee-9e30-4547-b36f-b471e4514e4c" />

### 20.5 On the same page, create an alert popup box appear on the page with your document cookies
**Answer:** `W3LL_D0N3_LVL2` and `websites_can_be_easily_defaced_with_xss`
<p align="center"> 
   <img width="463" height="203" alt="imagem" src="https://github.com/user-attachments/assets/fa07ba29-c246-441a-8c03-2d25a9b1740a" />
   <img width="449" height="217" alt="imagem" src="https://github.com/user-attachments/assets/75794969-bbc4-44a3-ad6e-91d8c9dcc067" />
   <img width="1318" height="570" alt="imagem" src="https://github.com/user-attachments/assets/7b4c7c8c-d191-4146-bb04-0da4842f5002" />
</p>

---

### 21.1 Who developed the Tomcat application? 
**Answer:** The Apache Software Foundation

### 21.2 What type of attack that crashes services can be performed with insecure deserialization?
**Answer:** Denial of Service

---

### 22.1 Select the correct term of the following statement: 
if a dog was sleeping, would this be:
A) A State
B) A Behaviour

**Answer:** A Behaviour 

---

### 23.1 What is the name of the base-2 formatting that data is sent across a network as?
**Answer:** binary

---

### 24.1 If a cookie had the path of webapp.com/login , what would the URL that the user has to visit be?
**Answer:** webapp.com/login

### 24.2 What is the acronym for the web technology that Secure cookies work over?
**Answer:** HTTPS

---

### In the browser of the device that you are connected to the VPN with, navigate to http://MACHINE_IP. I will be detailing the steps for Firefox — you may have to research how to inspect cookies in the browser of your choice. You will be greeted with the home page:
<p align="center"> 
   <img width="1649" height="757" alt="imagem" src="https://github.com/user-attachments/assets/84569e01-1325-4905-8672-2ca0be54dd65" />
   <img width="1919" height="717" alt="imagem" src="https://github.com/user-attachments/assets/8e209819-217b-4722-a773-8cf5ba85eb47" />
</p>

### 1st flag (cookie value)
**Answer:** `THM{good_old_base64_huh}`

### 2nd flag (admin dashboard)
**Answer:** `THM{heres_the_admin_flag}`

### 26.1 flag.txt
**Answer:** `4a69a7ff9fd68`

---

### 29.1 How many characters are in /etc/passwd (use wc -c /etc/passwd to get the answer)
**Answer:** `1611`
<p align="center">
   <img width="1649" height="757" alt="imagem" src="https://github.com/user-attachments/assets/be09aeb0-ce94-47de-979b-36695badfbed" />
</p>

---

### 30.1 What IP address is the attacker using?
**Answer:** 49.99.13.16

### 30.2 What kind of attack is being carried out? 
**Answer:** Brute Force

---
## Conhecimento 

Como cada tipo de vulnerabilidade funciona: Injections, XSS, Broken Auth, etc.

Ferramentas úteis no pentesting web: Burp, SQLite, navegadores com DevTools.

A importância de validar input, manter software atualizado, utilizar HTTPS, lidar com sessões/cookies de forma segura.

Boas práticas de mitigação: validação de input, least privilege, logging, monitorização, tratamento de erros seguro.

Importância de práticas defensivas mesmo quando se foca no ofensivo — entender como mitigar torna-se diferencial.
