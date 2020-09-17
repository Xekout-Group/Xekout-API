# Buscar informações da loja

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/store/:domain" %}
{% api-method-summary %}
Buscar informções da loja
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar as informações de uma loja cadastrada na Xekout.
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 200000,
  "status": "success",
  "store": {
    "company": "string",
    "domain": "string",
    "logo": "string",
    "whatsapp": "string",
    "app_type": "string",
    "email": "string",
    "shopify_domain": "string",
    "url_store": "string",
    "document": "string",
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
      "testimonies": "string",
      "enable_message_checkout": boolean,
      "message_checkout": "string",
      "message_checkout_color_text": "string",
      "message_checkout_text_align": "string",
      "message_checkout_color_background": "string",
      "header_background": "string",
      "header_color_text": "string",
      "footer_background": "string",
      "footer_color_text": "string"
    },
    "facebook": [
      {
        "id": integer,
        "uuid": "string",
        "tenant_id": integer,
        "pixel_name": "string",
        "pixel_id": "string",
        "payment_type": "string",
        "products": "string",
        "created_at": timestamp,
        "updated_at": "string",
        "event": "string",
        "app_id": integer,
        "token": "string",
        "username": "string"
      },
    ],
    "google": null,
    "discounts": {
      "card_active": boolean,
      "card": integer,
      "card_message": "string",
      "billet": integer,
      "billet_active": boolean,
      "billet_message": "string"
    },
    "tidio": null,
    "jivochat": null,
    "tawk": null,
    "smartlook": null,
    "hotjar": null,
    "polen": null,
    "goaffpro": null,
    "theme": {
      "name": "string",
      "directory": "string"
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

{
  "status": "error",
  "code": 404012,
  "message": "Not state avaliable for this query"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
O envio do parâmetro de consulta _UF ****_não é obrigatório, o seu envio é apenas para buscar as informações de um unico estado.
{% endhint %}

