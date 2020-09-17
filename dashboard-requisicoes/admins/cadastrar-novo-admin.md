---
description: Cadastrar novo admin na plataforma.
---

# 2.1.1. Cadastrar novo Admin

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/admins" %}
{% api-method-summary %}
Cadastrar Admin
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de um novo admin.
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
Nome do admin
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email do admin
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Senha usada para fazer login
{% endapi-method-parameter %}

{% api-method-parameter name="whatsapp" type="string" required=true %}
Número de telefone, para notificações or WhatsApp
{% endapi-method-parameter %}

{% api-method-parameter name="cpf" type="string" required=true %}
CPF do admin
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Admin cadastrado com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201001,
  "admin": {
    "id": integer,
    "uuid": "string",
    "name": "string",
    "email": "string",
    "cpf": "string",
    "cellphone": "string",
    "created_at": timestamp,
    "updated_at": timestamp
   }
  }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Não possui as devidas credenciais para concluir a operação.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404002,
  "message": "you don't have the necessary credentials"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
O código utilizado na resposta da requisição, é um código próprio do Xekout App, para definições e especificações de todos os códigos, acessar [Códigos Respostas](cadastrar-novo-admin.md).
{% endhint %}

