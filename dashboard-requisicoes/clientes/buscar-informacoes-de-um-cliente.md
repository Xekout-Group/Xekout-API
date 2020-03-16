---
description: Exibir as informações relacionadas a um cliente cadastrado na plataforma.
---

# 2.3.2. Buscar informações de um cliente

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/users/:uuid" %}
{% api-method-summary %}
Buscar Cliente
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca por um admin, por meio do código UUID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro do cliente.
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
  "user": {
    "id": integer,
    "uuid": "string",
    "name": "string",
    "email": "string",
    "phone": "998345513",
    "phone_code_id": integer,
    "cpf": "string",
    "token_access": "string",
    "remember_token": "string",
    "state_id": integer,
    "active": boolean,
    "gender": "string",
    "email_verified_at": timestamp
    "shopify_user_id": integer,
    "gateway_user_id": "string",
    "gateway_id": integer,
    "user_address_id": integer,
    "api_token": "string",
    "birth": date,
    "status": boolean,
    "created_at": timestamp,
    "updated_at": timestamp
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar nenhum cliente correspondente a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404014,
  "message": "user not found or not avaliable"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Clientes na plataforma Xekout App, são definidos como _users_.
{% endhint %}

