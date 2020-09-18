---
description: Exibir as informações relacionadas a um fatura na plataforma.
---

# Buscar informações de uma fatura

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/invoices/:uuid" %}
{% api-method-summary %}
Buscar fatura
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca de um fatura.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID único referente ao cadastro da fatura.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Prefix" type="string" required=false %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Busca concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200002,
  "invoice": [
    {
      "id": integer,
      "uuid": "string",
      "product_id": "string",
      "total": decimal,
      "status_id": integer,
      "validate": timestamp,
      "period": "string",
      "quantity_approved": integer,
      "tenant_id": integer,
      "start": timestamp,
      "end": timestamp,
      "billet_code": "string",
      "billet_url": "string",
      "billet_pdf": "string",
      "gateway_transaction_id": "string",
      "gateway_id": integer,
      "products": "string",
      "created_at": timestamp,
      "updated_at": timestamp
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não possível encontrar nenhum fatura, correspondente a essa consulta .
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}

{
  "status": "error",
  "code": 404000,
  "message": "Invoice for not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

