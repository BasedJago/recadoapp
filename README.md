# RecadoApp

**Versão:** 0.0.1 (v2.0 do código-fonte)  
**Publicador:** IAGO RABELO SOARES DE LIMA  
**Instalador:** `Output\SetupRecadoApp0.0.1.exe`  
**Repositório:** RecadoApp

## 📋 Descrição

Um mensageiro corporativo completo, 100% gratuito e sem limites — sem planos, sem assinaturas, sem propagandas. Perfeito para equipes que precisam de comunicação interna eficiente sem depender de serviços de terceiros ou depender de internet (funciona 100% local).

Com um recurso único de visualizador interno de anexos (DOCX, XLSX, PDF, CSV, imagens e muito mais), cliente de e-mail integrado (SMTP/IMAP), e espelhamento opcional com Firebase Firestore para acesso remoto, o RecadoApp substitui com sobra soluções pagas como sistemas de comunicados internos, quadros de aviso corporativos e até mesmo o e-mail interno para comunicados rápidos.

Tudo em uma janela nativa elegante (pywebview + Tailwind CSS), rodando como um servidor Flask local leve e rápido.

## ⚙️ Funcionalidades

- **Recados** — Criação, edição, exclusão e listagem de recados com destinatários específicos ou "Todos"
- **Anexos** — Upload, download e visualização interna de imagens, PDFs, DOCX, XLSX, CSV, TXT e mais
- **Visualizador Interno** — Parseia DOCX, XLSX, CSV sem dependências externas (apenas zipfile + xml nativos)
- **E-mail Integrado** — Cliente de e-mail embutido (IMAP para receber, SMTP para enviar) com cache local
- **Firebase Firestore** — Espelhamento bidirecional entre SQLite local e Firebase (fallback automático)
- **SQLite Local** — Banco de dados local com cache de leitura e retry contra travamentos em rede
- **Login Persistente** — Sessão mantida entre reinícios do app (login automático)
- **Notificações** — Popup nativo (tkinter) + som (winsound) para novos recados
- **Bandeja do Sistema** — Minimizar para a bandeja (pystray) com menu de contexto
- **Modo Escuro** — Alternância entre tema claro/escuro salvo no localStorage
- **Busca e Filtros** — Busca textual, filtros por não lidos, enviados, arquivados, com anexos
- **Recados Recorrentes** — Recados diários, semanais ou mensais automáticos
- **Arquivamento** — Arquivar/desarquivar recados por usuário
- **Relatório de Ciência** — Visualizar quem viu e quem deu ciência em cada recado
- **Re-notificação** — Reenviar notificação para quem ainda não viu
- **Gerenciamento de Usuários** — CRUD de usuários com papéis (admin/user)
- **Admin** — Gerenciar usuários, redefinir senhas, ver relatórios
- **Config.ini** — Configurações centralizadas (banco, e-mail, aparência, etc.)
- **Instância Única** — Previne múltiplas instâncias do app
- **Auto-fechamento** — Fechamento automático programado (horário configurável)

## 🚀 Métodos de Uso

### Instalação

1. Baixe o instalador `SetupRecadoApp0.0.1.exe` da página de Releases
2. Execute o instalador (privilégios de administrador necessários)
3. O app será instalado em `C:\SUED\RecadoApp\`
4. Um atalho será criado no Menu Iniciar e (opcionalmente) na Área de Trabalho

### Primeiro Acesso

- **Usuário:** `admin`
- **Senha:** `admin`
- Altere a senha após o primeiro login

### Uso Básico

1. **Login** — Faça login com seu usuário e senha
2. **Enviar Recado** — Clique no botão "Novo Recado", selecione destinatários, escreva a mensagem e anexe arquivos se necessário
3. **Visualizar** — Clique em qualquer recado na lista para ver detalhes, anexos e respostas
4. **Responder** — Dentro do detalhe do recado, use o campo de resposta
5. **Filtros** — Use os filtros no topo da lista (Todos, Não Lidos, Enviados, Arquivados)
6. **E-mail** — Configure SMTP/IMAP nas Configurações para usar o cliente de e-mail integrado
7. **Configurações** — Acesse pelo ícone de engrenagem para configurar banco, e-mail e mais

### Configuração de E-mail

Para usar o cliente de e-mail integrado, configure nas Configurações > Aba E-mail:
- **SMTP/IMAP:** Servidor, porta, e-mail e senha
- **Segurança:** TLS (padrão) ou SSL
- **Gmail:** Use senha de aplicativo (autenticação de 2 fatores necessária)

## 🛠️ Tecnologias

| Componente | Tecnologia |
|---|---|
| Backend | Python 3 + Flask |
| Interface | Tailwind CSS (via CDN) |
| Janela Nativa | pywebview |
| Banco Local | SQLite |
| Banco Cloud | Firebase Firestore |
| Autenticação | bcrypt |
| E-mail | smtplib + imaplib |
| Notificações | tkinter + winsound |
| Bandeja | pystray + Pillow |
| Visualizador | zipfile + xml.etree (nativos) |

## 📦 Estrutura de Instalação

```
C:\SUED\RecadoApp\
├── RecadoApp.exe          # Executável principal
├── config.ini             # Configurações (banco, e-mail, app)
├── icon.ico               # Ícone do aplicativo
├── firebase-key.json      # Credencial Firebase (opcional)
├── data.db                # Banco SQLite
├── attachments/           # Anexos dos recados
├── email_attachments/     # Anexos de e-mail
├── login.log              # Sessão persistente
├── quited.json            # Registro de desconexão do banco
├── emails.json            # Cache de e-mails (resumido)
├── emails_full.json       # Cache de e-mails (completo)
├── autoclose.json         # Configuração de auto-fechamento
├── log.txt                # Log do aplicativo
└── log_erro.txt           # Log de erros
```

## 📄 Licença

Todos os direitos reservados.
