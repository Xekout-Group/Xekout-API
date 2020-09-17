---
description: Buscar informações de um cliente.
---

# Buscar cliente

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/customer" %}
{% api-method-summary %}
Cadastrar Cliente
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint cadastrar um novo cliente. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter name="Cookies" type="string" required=true %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" type="number" required=true %}
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="store" type="string" required=true %}
Domínio da loja cadastrada na Xekout.
{% endapi-method-parameter %}

{% api-method-parameter name="customer\_id" type="number" required=true %}
Idenficador de cadastro do cliente no Shopify.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200000,
  "customer": {
    "name": "string",
    "cpf": "string",
    "phone": "string",
    "email": "string",
    "shopify_user_id": integer,
    "user_address_id": integer,
    "address": {
      "cep": "string",
      "address": "string",
      "number": "string",
      "complement": "string",
      "neighborhood": "string",
      "city": "string",
      "state": {
        "id": integer,
        "name": "string",
        "uf": "string"
      },
      "country": {
        "iso": "string",
        "iso3": "string",
        "name": "string",
        "nicename": "string",
        "numcode": "string",
        "phonecode": "string",
        "language": "string"
      }
    }
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400001,
  "message": "Customer id not present"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 401003,
  "message": "Origin can't be verified"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}

{
  "status": "error",
  "code": 404000,
  "message": "Customer not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Clientes na plataforma Xekout App, são definidos como _users_.
{% endhint %}

