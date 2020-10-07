# Buscar propriedades da loja

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/store/properties/:domain" %}
{% api-method-summary %}
Buscar propriedades da loja
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar as propriedades de uma loja cadastrada na Xekout por plataforma.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="domain" type="string" required=true %}
Dominío da loja cadastra na Xekout.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 200000,
  "status": "success",
  "properties": {
    "primary_locale": "pt-BR",
    "country_code": "BR",
    "country_name": "Brazil",
    "timezone": "(GMT-05:00) Eastern Time (US & Canada)",
    "currency": "BRL"
  }
}

{
  "code": 200000,
  "status": "error",
  "message": "Error on try get tenant properties"
}

{
  "status": "error",
  "code": 200000,
  "message": "Tenant not found"
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=405 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 4050000,
  "status": "error",
  "message": "Not avaliable for this platform"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

