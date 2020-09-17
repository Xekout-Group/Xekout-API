---
description: Verifica status do pedido após criação.
---

# Verificar status do pedido

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/orders/:domain/:order\_id" %}
{% api-method-summary %}
Verificar pedido
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite verificar o status do pedido após cadastro.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="order\_id" type="string" required=true %}
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

{% api-method-query-parameters %}
{% api-method-parameter name="type" type="string" required=true %}
Define o tipo de pedido, que pode ser do tipo BILLET, CARD, QRCODE ou REDIRECT. 
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 200003,
  "status": "success",
  "order": {
    "id": "ae93b86d-f435-44ba-909c-ec55800b55a4",
    "status": "created",
    "details": {
      "order_id": "string",
      "shopify_order_id": "string",
      "financial_status": "string",
      "frete": float,
      "cashback": float,
      "subtotal": float,
      "discount": float,
      "gateway_message": "string",
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
      "orderRedirect": [],
      "cashbackAmedigital": {
        "cashback": 0,
        "cashback_type": "string"
      },
      "gateway": {
        "name": "string",
        "description": "string",
        "logo": "string"
      },
      "payment": {
        "name": "string",
        "description": "",
        "code": "string",
        "class_icon": "string"
      },
      "config": {
        "thank_you_page": "string"
      },
      "orderStatus": {
        "name": "string",
        "description": "string",
        "class_color": "string"
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
    },
    "created_at": timestamp
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

{
  "code": 401003,
  "status": "error",
  "order": {
    "id": "193cccb9-4b3d-4c3a-b94e-1b96b09db258",
    "status": "timeout",
    "details": null,
    "created_at": "2020-09-17T18:35:57.148Z"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Valor para _type_, deve ser enviado de acordo com a forma de pagamento utilizada no momento da criação do pedido.
{% endhint %}

