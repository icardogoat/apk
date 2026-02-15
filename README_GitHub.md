# Configuração do GitHub para o Rei dos Canais

Para colocar seu app no ar e funcionando com a atualização automática, siga estes passos:

### 1. Criar o Repositório
Crie um novo repositório no seu GitHub chamado `rei-dos-canais` (ou o nome que preferir).

### 2. Subir os arquivos
Você pode subir todos os arquivos do projeto, mas os essenciais para a **página de download** e **atualização** estão na pasta `github/`:
- `github/index.html` (Site de download)
- `github/version.json` (Arquivo que o app lê para saber se tem atualização)

### 3. Ativar o GitHub Pages (Site de Download)
1. No seu repositório no GitHub, vá em **Settings** -> **Pages**.
2. Em "Build and deployment", escolha a branch `main` e a pasta `/ (root)` (ou se você subir apenas a pasta github em uma branch separada, selecione ela).
3. Salve. Em alguns minutos, seu site estará no ar (ex: `https://seu-usuario.github.io/rei-dos-canais/`).

### 4. Configurar o App
No arquivo `lib/services/update_service.dart`, você deve colocar o link **RAW** do seu `version.json`.
O link será parecido com este:
`https://raw.githubusercontent.com/SEU_USUARIO/rei-dos-canais/main/github/version.json`

### 5. Como lançar atualizações
1. Gere o novo APK no Flutter.
2. Vá em **Releases** no GitHub e crie uma nova versão (ex: `v1.0.1`).
3. Suba o APK lá e copie o link do download.
4. Atualize o `github/version.json` no seu repositório com a nova versão e o novo link do APK.
5. O App de todos os usuários vai detectar a mudança sozinho!
