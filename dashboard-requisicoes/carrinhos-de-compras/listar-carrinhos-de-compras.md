---
description: Listar todas os carrinhos de compras cadastrados na plataforma.
---

# 4.3. Listar carrinhos de compras

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/tenants" %}
{% api-method-summary %}
Listar todos os Carrinhos de Compras
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os carrinhos de compras cadastrados na plataforma.
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
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Listagem de lojas concluída com sucesso.
{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 200002,
  "carts": [
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
    },
    ...
  ]
}
```

{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar carrinhos de compras que correspondam a essa consulta.
{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404002,
  "message": "carts not found or not avaliable"
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
