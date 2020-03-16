---
description: Cadastrar novo carrinho de compras.
---

# 2.4.1. Cadastrar novo carrinho de compras

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/carts" %}
{% api-method-summary %}
Cadastrar carrinho de compras
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de um novo carrinho de compras.
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
Carrinho de compras cadastrado com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201014,
  "cart": {
    "id": integer,
    "uuid": "string",
    "product_id": integer,
    "product_title": "string",
    "product_quantity": integer,
    "product_value": decimal,
    "user_id": integer,
    "tenant_id": integer,
    "created_at": timestamp,
    "updated_at": timestamp,
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```text
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

