---
description: 'Atualizar senha de Admin, por meio do número do CPF.'
---

# Esqueci a senha

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/auth/forgot/password/{cpf}" %}
{% api-method-summary %}
Esqueci a senha
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite resetar a senha de um admin, por meio do número de cpf.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="cpf" type="string" required=true %}
Número do CPF do admin cadastrado na plataforma XekoutApp.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Senha atualizada com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200,
  "message": "Password update successfuly"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Parâmetro CPF não foi encontrado.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400020,
  "message": "Missing cpf parameter."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar Admin que corresponda a esta consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404001,
  "message": "Admin not found"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=422 %}
{% api-method-response-example-description %}
Não foi possível atualizar a senha do Admin.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 422001,
  "message": "Error on try to update password"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/auth/forgot/password/{CPF}" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404001,
  "message": "Admin not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

