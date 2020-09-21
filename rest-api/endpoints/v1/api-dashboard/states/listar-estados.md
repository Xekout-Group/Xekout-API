---
description: Listar todas os estados cadastrados na plataforma.
---

# Listar estados

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/states" %}
{% api-method-summary %}
Listar todos os estados
{% endapi-method-summary %}

{% api-method-description %}
Lista todos os estados salvos no banco.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Prefix" %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" required=true %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="uf" type="string" required=false %}
UF do estado para consulta.
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Nome do estado para consulta.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
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

{% endapi-method-response-example-description %}

```
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



