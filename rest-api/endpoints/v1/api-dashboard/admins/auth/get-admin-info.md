---
description: Exibir as informações relacionadas a um admin cadastrado na plataforma.
---

# Buscar informações de um admin

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/admins" %}
{% api-method-summary %}
Buscar Admin
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca por um admin, por meio do código UUID.
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
Buscar concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200002,
  "admin": [
    {
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
    }
  ]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar nenhum admin correspondente a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404001,
  "message": "admin not found or not avaliable"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

