---
description: Cadastrar um novo cliente na plataforma.
---

# 2.3.1. Cadastrar novo cliente

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/users/:uuid" %}
{% api-method-summary %}
Cadastrar Cliente
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint cadastrar um novo cliente.
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

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Nome do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
E-mail de cadastro do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Senha de cadastro do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=true %}
Número telefônico do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="phone\_code\_id" type="string" required=true %}
Código do número telefônico do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="cpf" type="string" required=false %}
Número do CPF do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="gender" type="string" required=false %}
Sexo do cliente
{% endapi-method-parameter %}

{% api-method-parameter name="domain" type="string" required=true %}
URL do domínio do Shopify
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Cadastro do cliente realizado com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201011,
  "user": {
    "id": integer,
    "uuid": "string"
    "name": "string",
    "email": "string",
    "phone": "string",
    "phone_code_id": "string",
    "cpf": "string",
    "gender": "string",
    "uuid": "string",
    "created_at": timestamp,
    "updated_at": timestamp
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não possível cadastrar o cliente, campos inválidos.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400007,
  "message": "field error or null data"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Clientes na plataforma Xekout App, são definidos como _users_.
{% endhint %}

