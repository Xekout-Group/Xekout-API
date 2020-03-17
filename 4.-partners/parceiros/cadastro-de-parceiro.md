---
description: Cadastrar novo parceiro na plataforma.
---

# 4.1.2. Cadastro de parceiro

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/partner/register" %}
{% api-method-summary %}
Cadastrar Parceiro
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de um novo parceiro.
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
{% api-method-parameter name="fullname" type="string" required=true %}
Nome completo do parceiro
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email do parceiro
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Senha usada para fazer login
{% endapi-method-parameter %}

{% api-method-parameter name="cellphone" type="string" required=true %}
Número de telefone do parceiro
{% endapi-method-parameter %}

{% api-method-parameter name="cpf" type="string" required=true %}
Número do CPF do parceiro
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Parceiro cadastrado com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201012,
  "partnerData": {
    "id": integer,
    "uuid": "string",
    "name": "string",
    "email": "string",
    "cpf": "string",
    "cellphone": "string",
    "created_at": timestamp,
    "updated_at": timestamp,
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Erro ao cadastrar um novo parceiro.
{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 400006,
  "message": "cpf or email for partner alread exist in database"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

