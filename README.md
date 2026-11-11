# Finanças Pessoais

App de controle financeiro pessoal: contas, cartões e faturas, despesas fixas e recorrentes, valores divididos com terceiros, vale-refeição, gastos da moto, metas, calendário, relatórios e projeções.

Ele é um **PWA** (Progressive Web App): funciona no navegador e pode ser instalado no celular (Android e iPhone) como um app comum, inclusive sem internet.

## Onde ficam os dados

- Os dados ficam **somente no aparelho** onde o app foi aberto (armazenamento local do navegador).
- **Nada é enviado ao GitHub.** O repositório guarda só o código do app.
- **Nunca envie o arquivo de backup (.json) para o repositório.** O `.gitignore` já bloqueia arquivos `.json`.
- Para levar os dados para outro aparelho, use **Exportar backup** e depois **Importar backup** no aparelho novo.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O app completo (telas, cálculos e estilos) |
| `manifest.webmanifest` | Nome, cores e ícones para instalar no celular |
| `sw.js` | Permite abrir o app sem internet |
| `icons/` | Ícones do app |
| `.nojekyll` | Faz o GitHub Pages publicar os arquivos como estão |
| `.gitignore` | Impede o envio de backups (.json) ao GitHub |

## 1. Publicar no GitHub Pages

1. Entre em [github.com](https://github.com) e clique em **New repository**.
2. Dê um nome, por exemplo `financas-pessoais`, e deixe como **Public** (o GitHub Pages gratuito exige repositório público; o código não contém nenhum dado seu).
3. Clique em **Create repository** e depois em **uploading an existing file**.
4. Arraste **todo o conteúdo desta pasta** (incluindo a pasta `icons`) e clique em **Commit changes**.
   - Os arquivos `.nojekyll` e `.gitignore` começam com ponto e podem ficar ocultos no seu computador. Se não aparecerem, crie-os pelo GitHub em **Add file → Create new file** (o `.nojekyll` pode ficar vazio).
5. Vá em **Settings → Pages**. Em **Branch**, escolha `main` e a pasta `/ (root)`. Clique em **Save**.
6. Aguarde 1 a 2 minutos. O endereço aparece no topo da página, no formato:
   `https://SEU-USUARIO.github.io/financas-pessoais/`

## 2. Instalar no celular

**Android (Chrome)**
1. Abra o endereço do app no Chrome.
2. Toque em **⋮ → Instalar app** (ou **Adicionar à tela inicial**).

**iPhone (Safari)**
1. Abra o endereço do app no **Safari** (precisa ser o Safari).
2. Toque em **Compartilhar → Adicionar à Tela de Início**.

## 3. Carregar seus dados

1. Abra o app instalado. Na primeira vez, aparece a tela de boas-vindas.
2. Toque em **Importar backup** e escolha o arquivo `financas-pessoais-backup-AAAA-MM-DD.json`.
   - Envie o arquivo para o celular por e-mail, WhatsApp, Google Drive ou cabo, e salve em **Arquivos/Downloads**.
3. Confirme. Todos os lançamentos, contas, cartões, recorrências, metas e dados da moto aparecem.

## 4. Backup (importante)

- Como os dados ficam só no aparelho, **exporte um backup com frequência**: aba **Categorias e dados → Backup (JSON)**.
- O app avisa quando o último backup tem mais de 7 dias.
- Limpar os dados do navegador ou desinstalar o app **apaga os dados**. Guarde os backups no Google Drive, iCloud ou e-mail.
- Também é possível exportar **CSV** e **Excel (.xlsx)** para consulta.

## 5. Atualizar o app

1. Substitua o `index.html` (e os demais arquivos alterados) no repositório.
2. Abra o `sw.js` e aumente a versão em `const CACHE='fp-v1.0.0'` (por exemplo, `fp-v1.0.1`).
3. No celular, feche e abra o app duas vezes para carregar a nova versão. Os dados não são afetados.

## Opcional: gerar um APK para Android

Com o app já publicado no GitHub Pages, acesse [pwabuilder.com](https://www.pwabuilder.com), cole o endereço do app e use **Package for stores → Android**. Ele gera um APK que instala o mesmo app.

## Próximos passos possíveis

Para sincronizar automaticamente entre celular e computador, com login, o caminho recomendado é ligar o app a um banco com autenticação (por exemplo, Supabase). O GitHub continua guardando apenas o código.
