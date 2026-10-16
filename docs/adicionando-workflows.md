# Adicionando e compartilhando workflows

## Exportar do N8N

No workflow, abra o menu e escolha **Download** para gerar o arquivo `.json`.

## Checklist antes de publicar (obrigatório)

Antes de colocar qualquer workflow neste repositório, remova ou troque:

- [ ] IDs de credenciais (`"credentials": { "tipo": { "id": ... } }`). Mantenha só o nome genérico.
- [ ] Tokens, chaves de API, senhas e segredos em qualquer nó.
- [ ] URLs reais de webhook. Use um caminho genérico, como `whatsapp-agente`.
- [ ] IDs de planilhas, calendários, listas e contas (Google, ClickUp, etc.).
- [ ] Números de telefone, e-mails e nomes de clientes.
- [ ] Textos de prompt com nomes de empresas e informações internas. Use campos como `[NOME_DA_EMPRESA]`.
- [ ] Os campos `id`, `versionId` e `meta.instanceId` do workflow.
- [ ] Dados de teste (`pinData`). Deixe vazio: `"pinData": {}`.
- [ ] `"active": false`, para o workflow importar desativado.

O CI do repositório rejeita workflows com ID de credencial, mas a revisão final é sua.

## Nome e numeração

Use o padrão `NN-descricao-curta.json` na pasta `workflows/` (por exemplo, `02-lembrete-24h.json`) e adicione uma linha na tabela do README.

## Importação automática

Só o arquivo indicado em `WORKFLOWS_IMPORT_URL` é importado sozinho. Os demais são importados manualmente pelo usuário: **Workflows → Import from file**.
