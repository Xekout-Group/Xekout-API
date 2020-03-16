---
description: Cadastrar novo pedido.
---

# 2.6.1. Cadastrar novo pedido

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/orders" %}
{% api-method-summary %}
Cadastrar pedido
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de um novo pedido.
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
Pedido cadastrado com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201007,
  "order": {
    "id": integer,
    "uuid": "string",
    "order_payment_id": integer,
    "user_id": integer,
    "discount": decimal,
    "subtotal": decimal,
    "frete": decimal,
    "total": decimal,
    "tenant_id": integer,
    "created_at": timestamp,
    "updated_at": timestamp
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não possível cadastrar o pedido, campos inválidos.
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

