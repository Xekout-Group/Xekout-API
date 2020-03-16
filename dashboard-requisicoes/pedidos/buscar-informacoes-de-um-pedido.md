---
description: Exibir as informações relacionadas a um pedido na plataforma.
---

# 2.6.2. Buscar informações de um pedido

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/orders/:uuid" %}
{% api-method-summary %}
Buscar Pedido
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca de um pedido, por meio do código UUID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro do pedido.
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
      "uuid": "string",
      "order_id": integer,
      "name": "string",
      "total": decimal,
      "order_status_id": integer,
      "created_at": timestamp
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não possível encontrar nenhum pedido, correspondente a essa consulta .
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404010,
  "message": "order not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

