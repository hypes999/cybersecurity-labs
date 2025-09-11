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
<img width="718" height="264" alt="imagem" src="https://github.com/user-attachments/assets/c3a15b22-2a41-4684-9ec6-a26c1e4efe16" />
<img width="713" height="246" alt="imagem" src="https://github.com/user-attachments/assets/fb0601db-5b81-475f-a3a3-1f66fffc3ba8" />
<img width="710" height="511" alt="imagem" src="https://github.com/user-attachments/assets/8dee56ed-24b5-4df2-8275-1b76a9b48123" />
<img width="738" height="281" alt="imagem" src="https://github.com/user-attachments/assets/dbeedbb6-ca82-4a36-be62-45b3453e5b9b" />
<img width="289" height="887" alt="imagem" src="https://github.com/user-attachments/assets/3e0e431d-38a0-4dd7-84a5-943fa07c39ec" />



## Conhecimento / Aprendizados

Como cada tipo de vulnerabilidade funciona: Injections, XSS, Broken Auth, etc.

Ferramentas úteis no pentesting web: Burp, SQLite, navegadores com DevTools.

A importância de validar input, manter software atualizado, utilizar HTTPS, lidar com sessões/cookies de forma segura.

Boas práticas de mitigação: validação de input, least privilege, logging, monitorização, tratamento de erros seguro.

Importância de práticas defensivas mesmo quando se foca no ofensivo — entender como mitigar torna-se diferencial.
