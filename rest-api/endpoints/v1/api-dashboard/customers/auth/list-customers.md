---
description: Listar todos os clientes cadastrados na plataforma.
---

# Listar clientes

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/users" %}
{% api-method-summary %}
Listar todos os Clientes
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os clientes cadastrados na plataforma.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" type="string" required=true %}
Sub domínio da loja cadastrada.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Prefix" type="string" required=false %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer Token JWT para autenticação
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="perPage" type="string" required=false %}
Número de itens por página
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
Número da página da lista
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Listagem de clientes concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200003,
  "items": [
    {
      "name": "string",
      "id": integer,
      "cpf": "string",
      "email": "string",
      "phone": "string",
      "phone_code_id": integer,
      "store_user_token": "string",
      "created_at": timestamp,
      "updated_at": timestamp
    },
    ...
  ],
  "total": integer,
  "perPage": integer,
  "page": integer,
  "lastPage": integer,
  "platform": integer
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Clientes na plataforma Xekout App, são definidos como _users_.
{% endhint %}

