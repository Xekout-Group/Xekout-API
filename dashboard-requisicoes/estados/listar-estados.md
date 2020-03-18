---
description: Listar todas os estados cadastrados na plataforma.
---

# 2.7.2. Listar estados

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/orders" %}
{% api-method-summary %}
Listar todos os Estados
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os estados cadastrados na plataforma.
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
Listagem de estados concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200003,
  "states": [
    {
      "id": integer,
      "name": "string",
      "uf": "string",
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
Não foi possível encontrar estados que correspondam a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404012,
  "message": "states not found or not avaliable"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

