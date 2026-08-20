---
name: registradores_matric_recibo-mcp
description: Skill da REST API do Registradores (ARISP) Matrícula: Download de Recibo na MCP.AI: 1 endpoint em /api/registradores_matric_recibo. Registradores (ARISP) Matrícula: Download de Recibo, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Registradores (ARISP) Matrícula: Download de Recibo — REST API skill

Você tem acesso à **Registradores (ARISP) Matrícula: Download de Recibo** REST API na MCP.AI.

> Registradores (ARISP) Matrícula: Download de Recibo, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/registradores_matric_recibo
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/registradores_matric_recibo/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/registradores_matric_recibo/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `registradores_matric_recibo_consultar`

Registradores (ARISP) Matrícula: Download de Recibo, consulta em fonte oficial. _(POST /api/registradores_matric_recibo/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `email` | string | Não | Parâmetro de consulta "email". |
| `senha` | string | Não | Parâmetro de consulta "senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |
| `tipo_login` | string | Não | Parâmetro de consulta "tipo_login". |
| `numero_pedido` | string | Não | Parâmetro de consulta "numero_pedido". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_registradores_matric_recibo` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
