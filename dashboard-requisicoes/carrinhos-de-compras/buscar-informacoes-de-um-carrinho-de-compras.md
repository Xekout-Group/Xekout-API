---
description: Exibir as informações relacionadas a um carrinho de compras na plataforma.
---

# 2.4.2. Buscar informações de um carrinho de compras

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/carts/:uuid" %}
{% api-method-summary %}
Buscar Carrinho de Compras
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca de um carrinho de compras, por meio do código UUID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro do carrinho de compras.
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
  "cart": [
    {
      "id": integer,
      "uuid": "string",
      "product_id": "string",
      "product_title": "string",
      "product_quantity": integer,
      "product_image": "string",
      "product_variant_id": integer,
      "product_type": "string",
      "product_url": "string",
      "product_discount": decimal,
      "product_value": decimal,
      "product_observation": "string",
      "cart_token": "string",
      "user_id": integer,
      "tenant_id": integer,
      "hostname_id": integer,
      "created_at": timestamp,
      "updated_at": timestamp
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não possível encontrar nenhum carrinho de compras, correspondente a essa consulta .
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404002,
  "message": "cart not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

