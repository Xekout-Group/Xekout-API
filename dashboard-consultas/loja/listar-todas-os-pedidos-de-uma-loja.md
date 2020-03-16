# 3.3.1. Listar todas os pedidos de uma loja

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/search/tenant/orders/:uuid" %}
{% api-method-summary %}
Listar pedidos de uma loja
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os pedidos de uma loja.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro da loja na plataforma.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Prefix" %}
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
  "code": 200003,
  "orders": [
    {
      "shopify_id": "string",
      "order_status_id": integer,
      "name": "string",
      "email": "string",
      "phone": "string",
      "total": decimal,
      "created_at": timestamp,
    },
    ...
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
UUID inválido ou não existe.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400010,
  "message": "this uuid is invalid for this request"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar nenhum pedido correspondente a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404104,
  "message": "no orders available for this tenant"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

