# Solução de problemas

## O nó da Evolution API aparece como "desconhecido"

A instalação automática pode ter falhado. Veja os logs:

```bash
docker compose logs n8n | grep "\[setup\]"
```

Se aparecer o aviso de falha, instale manualmente: no N8N, **Settings → Community Nodes → Install**, digite `n8n-nodes-evolution-api` e confirme. Depois reinicie o N8N.

## O workflow não apareceu no N8N

A importação automática baixa o arquivo de `WORKFLOWS_IMPORT_URL`. Verifique:

- Se a variável aponta para o link "raw" correto do seu repositório (público).
- Os logs: `docker compose logs n8n | grep "\[setup\]"`.

Se falhar, importe manualmente: **Workflows → Import from file** com o arquivo da pasta `workflows/`.

Para forçar uma nova tentativa automática, apague o marcador e reinicie:

```bash
docker compose exec n8n rm /home/node/.n8n/.workflow-imported
docker compose restart n8n
```

Isso importa o workflow de novo, criando uma cópia.

## O agente não responde

1. O workflow está **ativo**?
2. O webhook da instância aponta para `http://n8n:5678/webhook/whatsapp-agente` e o evento `MESSAGES_UPSERT` está marcado?
3. A credencial da OpenAI é válida e tem saldo?
4. Veja as execuções em **Executions** no N8N para achar o nó com erro.

## O Caddy não emite o certificado

- Os registros DNS tipo A estão apontando para o IP do servidor?
- As portas 80 e 443 estão abertas no firewall e livres no servidor?
- Veja: `docker compose logs caddy`.

## Erro ao criar a tarefa no ClickUp

O nó usa o campo `status`. Ajuste para um status que exista na sua lista do ClickUp.

## Perdi o acesso às credenciais depois de reinstalar

As credenciais só podem ser lidas com a mesma `N8N_ENCRYPTION_KEY` usada quando foram criadas. Guarde essa chave junto com os backups.

## Mensagens de áudio não são transcritas

Confirme que a credencial da OpenAI está selecionada nos nós **Transcribe a recording**, **Analyze image** e **Generate audio**, e que a instância da Evolution API consegue baixar mídia (nó **Obter midia em base64**).
