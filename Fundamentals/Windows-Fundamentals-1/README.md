# Windows Fundamentals Part I

Este módulo explora conceitos fundamentais do sistema Windows, incluindo a interface gráfica, sistema de ficheiros, contas de usuário, controlo de contas (UAC), Painel de Controlo e Gestor de Tarefas.

## Objetivos
- Compreender funcionalidades distintas das edições Windows Home vs Pro (como BitLocker).
- Navegar na interface do Windows e seu sistema de ficheiros (NTFS).
- Identificar variáveis de ambiente importantes (`%windir%`).
- Gerir contas de utilizador, permissões e UAC.
- Navegar no Painel de Controlo e usar Gestor de Tarefas.

## Passo a passo
1. Identificar recursos exclusivos do Windows Pro, como o **BitLocker**.
2. Explorar o ambiente gráfico (GUI): ocultar a barra de pesquisa, botão Task View e ícone no centro de notificações.
3. Compreender o sistema de ficheiros usado (NTFS) e suas vantagens.
4. Verificar a variável de ambiente do diretório Windows (`%windir%`) e conteúdo da pasta System32.
5. Usar o `lusrmgr.msc` para inspecionar contas, grupos e descrições de usuários.
6. Entender o controlo de contas (UAC) e quando é necessário.
7. Alternar para visualização de ícones pequenos no Painel de Controlo e identificar a última entrada (Windows Defender Firewall).
8. Aprender o atalho de teclado para abrir o Task Manager (Ctrl + Shift + Esc).

## Comandos e Ferramentas

```powershell
# Abrir o gestor de utilizadores
lusrmgr.msc

# Não há outros comandos específicos documentados no walkthrough; a navegação foi feita via GUI e inspeção visual.

