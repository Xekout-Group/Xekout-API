---
description: Listar todas os pedidos cadastrados na plataforma.
---

# 2.6.3. Listar pedidos

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/orders" %}
{% api-method-summary %}
Listar todos os Pedidos
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os pedidos cadastrados na plataforma.
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

```text
{
  "status": "success",
  "code": 200003,
  "orders": [
    {
      "uuid": "string",
      "order_id": integer,
      "name": "string",
      "total": decimal,
      "order_status_id": integer,
      "created_at": timestamp
    },
    ...
  ]
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

