---
description: Cadastrar novo admin na plataforma.
---

# Cadastrar novo Admin

{% api-method method="post" host="https://dapi.xekout.app" path="/v1/admin/admins" %}
{% api-method-summary %}
Cadastrar Admin
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de um novo admin.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="user" type="object" required=true %}
Objeto contendo as informações do admin
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
    "name": "string",
    "email": "string",
    "cpf": "string",
    "cellphone": "string",
    "status": boolean400
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404002,
  "message": "CPF is invalid"
}

{
  "status": "error",
  "code": 400001,
  "message": {
    "user": "Mensagem de erro
    "
  }
}

{
  "status": "error",
  "code": 404002,
  "message": "Error on try register admin and tenant"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Objeto **user** para referencia:

| Tipo | Nome | Descrição |
| :--- | :--- | :--- |
| string | name | Nome do admin |
| string | email | Email do admin |
| string | cpf | CPF do admin |
| string | password | Senha de acesso do admin |
| string | whatsapp | Número de telefone |

{% hint style="info" %}
O código utilizado na resposta da requisição, é um código próprio do Xekout App, para definições e especificações de todos os códigos, acessar [Códigos Respostas](register-new-admin.md).
{% endhint %}



