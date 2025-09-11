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

## Comandos e scripts usados (exemplos)

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
´´´
