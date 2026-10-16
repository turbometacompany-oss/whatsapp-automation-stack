# Política de segurança

## Reportando uma vulnerabilidade

Se você encontrar uma falha de segurança neste repositório (por exemplo, credenciais expostas em um workflow ou configuração insegura no `docker-compose.yml`), **não abra uma issue pública**.

Use a opção **Report a vulnerability** na aba **Security** do repositório ou envie um e-mail para sac@turbometacompany.com.br, informando:

- descrição do problema
- passos para reproduzir
- impacto estimado

Responderemos assim que possível.

## Boas práticas para quem usa a stack

- Troque todas as senhas e chaves padrão (`troque-...`) antes de usar em produção.
- Use domínio com HTTPS e `PUBLIC_BIND_IP=127.0.0.1`.
- Mantenha o servidor e as imagens atualizados.
- Faça backup do banco de dados e da `N8N_ENCRYPTION_KEY`.
- Nunca publique `.env`, chaves de API ou dados de clientes.
