---
description: Listar todas os estados cadastrados na plataforma.
---

# Listar estados

{% api-method method="get" host="https://api.xekout.app" path="/v1/admin/states" %}
{% api-method-summary %}
Listar todos os Estados
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os estados cadastrados na plataforma.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter type="string" name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter type="string" name="Cookies" required=true %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter type="string" name="X-Request-Number" required=true %}
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="store" type="string" required=true %}
Domínio da loja cadastrada na Xekout, codificado em base64.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 200003,
  "states": [
    {
      "id": integer,
      "name": "string",
      "uf": "string",
      "created_at": timestamp,
      "updated_at": timestamp
    },
    ...
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404012,
  "message": "states not found or not avaliable"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

