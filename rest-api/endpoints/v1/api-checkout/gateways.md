---
description: Lista todos os meios de pagamento que a loja está utilizando.
---

# Gateways

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/gateways" %}
{% api-method-summary %}
Listar meios de pagamento
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint lista todos os meios de pagamento cadastrados pelo lojista.
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
  "code": 200,
  "gateways": {
    "billet": {
      "installments": integer,
      "key_production": "string",
      "logo": "string",
      "description": "string",
      "name": "string",
      "code": "string",
      "id": integer
    },
    "card": {
      "installments": integer,
      "key_production": "string",
      "logo": "string",
      "description": "string",
      "name": "string",
      "code": "string",
      "id": integer
    },
    "amedigital": {
      "cashback": float,
      "cashback_type": "string",
      "logo": "string",
      "description": "string",
      "name": "string",
      "code": "string",
      "id": integer
    },
    "picpay": {
      "logo": "string",
      "description": "string",
      "name": "string",
      "code": "string",
      "id": string
    },
    "paypal": {
      "logo": "string",
      "description": "string",
      "name": "string",
      "code": "string",
      "id": integer
    }
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 401003,
  "status": "error",
  "message": "Origin can't be verified"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{
  "code": 404000,
  "status": "error",
  "message": "Tenant not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



