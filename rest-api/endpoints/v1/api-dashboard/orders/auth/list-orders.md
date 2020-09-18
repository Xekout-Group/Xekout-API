---
description: Listar todas os pedidos cadastrados na plataforma.
---

# Listar pedidos

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/orders/:subdomain" %}
{% api-method-summary %}
Listar todos os Pedidos
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os pedidos cadastrados na plataforma.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" type="string" required=true %}
Sub domínio da loja cadastrada na Xekout.
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

{% api-method-query-parameters %}
{% api-method-parameter name="perPage" type="string" required=false %}
Quantidade de itens por página.
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
Número da página.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200003,
  "items": [
    {
      "id": integer,
      "total": float,
      "created_at": timestamp,
      "order_payment_id": integer,
      "order_status_id": integer,
      "user": {
        "id": integer,
        "name": "string",
        "email": "string",
        "phone": "string",
        "address": null
      },
      "orderStatus": {
        "name": "string",
        "class_color": "string"
      },
      "payment": {
        "class_icon": "string"
      },
      "products": [
        {
          "id": integer,
          "uuid": "string",
          "order_id": integer,
          "product_id": "string",
          "product_title": "string",
          "product_image": "string",
          "product_type": "string",
          "product_variant_id": "string",
          "product_quantity": "string",
          "product_url": "string",
          "product_value": integer,
          "product_discount": float,
          "product_observation": "string",
          "created_at": timestamp,
          "updated_at": timestamp
        }
      ]
    }
  ],
  "total": integer,
  "perPage": integer,
  "page": integer,
  "lastPage": integer,
  "platform": integer
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar pedidos que correspondam a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404010,
  "message": "orders not found or not avaliable"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



