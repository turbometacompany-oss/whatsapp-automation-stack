# Contribuindo

Obrigado por querer contribuir.

## Como contribuir

1. Faça um fork do repositório.
2. Crie uma branch: `git checkout -b minha-melhoria`.
3. Faça suas alterações e teste a stack com `docker compose up -d`.
4. Se mexer em workflows, siga o checklist de [docs/adicionando-workflows.md](docs/adicionando-workflows.md).
5. Abra um Pull Request descrevendo o que mudou e como testou.

## Regras importantes

- Nunca inclua credenciais, tokens, IDs reais, telefones ou dados de clientes.
- Mantenha o `docker-compose.yml` funcionando só com valores padrão e variáveis de ambiente (o botão da Hostinger lê apenas esse arquivo).
- Atualize o README e o CHANGELOG quando a mudança afetar o uso.

## Reportando problemas

Use as issues do GitHub e preencha o modelo. Para falhas de segurança, siga o [SECURITY.md](SECURITY.md).
