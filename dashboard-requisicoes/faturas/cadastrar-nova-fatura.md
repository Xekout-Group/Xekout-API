---
description: Cadastrar nova fatura.
---

# 2.5.1. Cadastrar nova fatura

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/orders" %}
{% api-method-summary %}
Cadastrar fatura
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de uma nova fatura.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
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
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Fatura cadastrado com sucesso.
{% endapi-method-response-example-description %}

```text
{
    "total" : decimal,
    "status_id" : "string",
    "validate": "string",
    "period": "string",
    "quantity_approved": "string",
    "tenant_id": integer,
    "start": timestamp,
    "end": timestamp,
    "billet_code": "string",
    "billet_url": "string",
    "billet_pdf": "string",
    "gateway_transaction_id": "string",
    "gateway_id": integer,
    "products": "string"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não possível cadastrar a fatura, campos inválidos.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400007,
  "message": "field error or null data"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

