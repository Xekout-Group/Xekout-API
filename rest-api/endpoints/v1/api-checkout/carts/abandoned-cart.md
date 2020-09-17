---
description: Busca as informações de um carrinho abandonado.
---

# Carrinho Abandonado

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/carts/:domain/abandoned/get/:token" %}
{% api-method-summary %}
Buscar carrinho abandonado
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint busca informações de um carrinho abandonado.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="domain" type="string" required=true %}
Domínio da loja cadastrada na XekoutApp.
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
Token do carrinho.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado
{% endapi-method-parameter %}

{% api-method-parameter required=true name="Cookies" %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" required=true %}
Identificador do estado enviado no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 200003,
  "cart": {
    "id": integer,
    "cart_token": "string",
    "user_id": integer,
    "tenant_id": integer,
    "hostname_id": null,
    "created_at": timestamp,
    "updated_at": timestamp,
    "has_discount": boolean,
    "original_price": float,
    "item_count": integer,
    "products": [
      {
        "product_id": integer,
        "product_title": "string",
        "product_quantity": integer,
        "product_image": "string",
        "product_variant_id": integer,
        "product_type": "string",
        "product_url": "string",
        "product_discount": float,
        "product_value": float,
        "product_observation": "string",
        "cart_id": integer,
        "created_at": timestamp,
        "has_discount": 0
      }
    ]
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 401003,
  "message": "Origin can't be verified"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404004,
  "message": "Cart abandoned not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



