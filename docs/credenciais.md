# Como criar as credenciais

Todas as credenciais são criadas dentro do N8N, em **Credentials → Create credential**. Elas ficam criptografadas com a sua `N8N_ENCRYPTION_KEY`.

## OpenAI

1. Acesse a plataforma da OpenAI e crie uma chave de API.
2. No N8N, crie a credencial **OpenAI** e cole a chave.
3. O workflow usa modelos de chat, transcrição de áudio, análise de imagem e geração de voz. Confirme que sua conta tem saldo.

## Redis

Crie a credencial **Redis** com:

- Host: `redis`
- Porta: `6379`
- Senha: em branco

## Evolution API

Crie a credencial **Evolution API** com:

- URL: `http://evolution-api:8080` (endereço interno entre os containers)
- API Key: o valor de `EVOLUTION_API_KEY`

## Google Sheets e Google Calendar

Os dois usam OAuth2. O caminho resumido:

1. No Google Cloud Console, crie um projeto e ative as APIs **Google Sheets** e **Google Calendar**.
2. Configure a tela de consentimento OAuth e adicione seu e-mail como usuário de teste.
3. Crie um **ID do cliente OAuth** do tipo "Aplicativo da Web".
4. Em "URIs de redirecionamento autorizados", cole a URL de callback que o N8N mostra na tela da credencial. Ela depende do seu `N8N_WEBHOOK_URL`, por isso configure o domínio antes.
5. Copie o Client ID e o Client Secret para a credencial no N8N e clique em **Sign in with Google**.

Para o Google Calendar, o evento é criado no calendário que você selecionar no nó. Para o Google Sheets, a planilha precisa ter na primeira linha as colunas `Nome`, `Telefone`, `Data e hora`, `Tipo de negócio` e `Cidade e região`.

## ClickUp

1. No ClickUp, gere um token pessoal de API nas configurações do seu perfil.
2. No N8N, crie a credencial **ClickUp** e cole o token.
3. No nó **Create a task in ClickUp**, escolha Team, Space, Folder e List.
4. O campo `status` precisa ser um status que exista na sua lista.
