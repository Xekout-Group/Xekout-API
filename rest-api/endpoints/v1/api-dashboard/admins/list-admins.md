---
description: Listar todos os admins cadastrados na plataforma.
---

# Listar admins

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/admins" %}
{% api-method-summary %}
Listar todos os Admins
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os admins cadastrados na plataforma.
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
Listagem de admins concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200003,
  "admins": [
    {
      "id": integer,
      "uuid": "string",
      "name": "string",
      "cpf": "string",
      "gateway_id": integer,
      "gateway_method_id": integer,
      "email": "string",
      "cellphone": "string",
      "cep": "string",
      "address": "string",
      "number": "string",
      "complement": "string",
      "neighborhood": "string",
      "city": "string",
      "state_id": integer,
      "token_access": "string",
      "remember_token": "string",
      "status": boolean,
      "gender": "string",
      "email_verified_at": timestamp,
      "login_at": timestamp,
      "shopify_user_id": integer,
      "file_id": integer,
      "gateway_user_id": integer,
      "created_at": timestamp,
      "updated_at": timestamp
    }
    ...
  ]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar Admins que correspondam a esta consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404001,
  "message": "admins not found or not avaliable"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

