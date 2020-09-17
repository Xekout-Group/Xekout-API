# Buscar pedido cadastrado

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/orders/:domain/:id" %}
{% api-method-summary %}
Buscar pedido por identificador
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar um pedido cadastrado
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Idenficador do pedido no shopify, salvo no campo _shopify\_user\_id_ salvo no banco.
{% endapi-method-parameter %}

{% api-method-parameter name="domain" type="string" required=true %}
Domínio da loja cadastrada na Xekout
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter name="Cookies" required=true type="string" %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" required=true type="string" %}
Identificador do estado enviado no Cookies.
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
  "order": {
    "info": [
      {
        "order_id": "string",
        "financial_status": "string",
        "frete": float,
        "subtotal": float,
        "discount": float,
        "end_card": "string",
        "installments": integer,
        "flag": "string",
        "shopify_url": "string",
        "created_at": timestamp,
        "user": {
          "name": "string",
          "email": "string",
          "cpf": "string",
          "phone": "string",
          "address": {
            "cep": "string",
            "address": "string",
            "number": "string",
            "complement": "string",
            "neighborhood": "string",
            "city": "string",
            "country": {
              "iso": "string"
            },
            "state": {
              "name": "string",
              "uf": "string"
            }
          }
        },
        "orderBillet": [],
        "orderQrcode": [],
        "cashbackAmedigital": float,
        "gateway": {
          "name": "string",
          "description": "string",
          "logo": "string"
        },
        "payment": {
          "name": "string",
          "description": "string",
          "code": "string",
          "class_icon": "string"
        },
        "config": {
          "thank_you_page": "string
        },
        "products": [
          {
            "product_id": "string",
            "product_title": "string",
            "product_image": "string",
            "product_type": "string",
            "product_variant_id": "string",
            "product_quantity": "string",
            "product_url": "string"
          }
        ]
      }
    ]
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



