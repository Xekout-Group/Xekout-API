---
description: Exibir as informações relacionadas a um carrinho de compras na plataforma.
---

# Buscar informações de um carrinho de compras

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/carts/:subdomain/:id" %}
{% api-method-summary %}
Buscar Carrinho de Compras
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca de um carrinho de compras.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" type="string" required=true %}
Subdomínio da loja cadastrada.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
ID único referente ao cadastro do carrinho de compras.
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
  "cart": {
    "cart_token": "string",
    "item_count": integer,
    "original_price": float,
    "created_at": timestamp,
    "products": [
      {
        "product_id": inetegr,
        "product_variant_id": integer,
        "product_quantity": integer,
        "product_value": float,
        "product_image": "string"
      }
    ],
    "user": {
      "name": "string",
      "id": integer,
      "email": "string",
      "phone": "string"
    }
  },
  "platform": integer
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404000,
  "message": "Cart for not found"
}

{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

