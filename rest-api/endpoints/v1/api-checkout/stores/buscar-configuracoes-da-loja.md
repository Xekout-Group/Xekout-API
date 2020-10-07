# Buscar configurações da loja

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/store/config/:domain" %}
{% api-method-summary %}
Buscar configurações da loja
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar as configurações salvas de uma loja cadastrada na Xekout.
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
  "config": {
      "back_store": boolean,
      "safe": boolean,
      "plots": boolean,
      "phone": boolean,
      "enable_coupon": boolean,
      "coupon": "string",
      "product_note": boolean,
      "product_quantity": boolean,
      "scarcity": boolean,
      "scarcity_time": "string",
      "shipping": boolean,
      "scarcity_color_background": "string",
      "scarcity_color_text": "string",
      "scarcity_text_align": "string",
      "scarcity_message": "string",
      "testimonies": object",
      "enable_message_checkout": boolean,
      "message_checkout": "string",
      "message_checkout_color_text": "string",
      "message_checkout_text_align": "string",
      "message_checkout_color_background": "string",
      "header_background": "string",
      "header_color_text": "string",
      "footer_background": "string",
      "footer_color_text": "string"
    }
}

{
  "code": 200000,
  "status": "error",
  "message": "No config found"
}

{
  "status": "error",
  "code": 200000,
  "message": "Error on try get tenant config"
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
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

