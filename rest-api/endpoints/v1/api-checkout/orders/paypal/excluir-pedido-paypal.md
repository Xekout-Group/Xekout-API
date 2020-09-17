---
description: 'Quando o pedido não é executado, ele precisa ser excluido.'
---

# Excluir pedido PayPal

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/orders/paypal/:order\_id/delete" %}
{% api-method-summary %}
Excluir pedido PayPal
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint executar um pagamento para pedido utilizando PayPal.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="order\_id" type="string" required=true %}
Idenficador do pedido cadastrado na Xekout.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter name="Cookies" required=true %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" required=true %}
Identificador do estado enviado no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 400000,
  "status": "error",
  "message": "Order not valid to tenant"
}


{
  "code": 400000,
  "status": "error",
  "message": "Error on try register order"
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
  "code": 404000,
  "status": "error",
  "message": "Order not found"
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Abaixo modelo completo do objeto _**order**_.

```text
{
	"paymentType": {
		"id": integer,
		"code": "string"
	},
	"gatewayType": {
		"id": integer,
		"code": "string"
	},
	"card": {
		"card_token": "string",
		"brand": "string",
		"installments": integer,
		"flag": "string",
		"end_card": "string",
		"taxes": {
			"price": float,
			"title": "string"
		}
	},
	"note": "string",
	"customer": {
		"id": integer
	},
	"shipping": boolean,
	"cart": {
		"shipping": {
			"code": "string",
			"value": float,
			"name": "string"
		},
		"cart_token": "string",
		"total_cart_price": "string",
		"total_cart_discount": "string",
		"final_cart_price": "string",
		"currency": "string",
		"discount": {
			"coupon_id": integer,
			"coupon_code": "string",
			"coupon_type": "string",
			"coupon_amount": "string"
		},
		"products": [
			{
				"product_id": integer,
				"variant_id": integer,
				"title": "string",
				"quantity": integer,
				"image_url": "string",
				"original_price": "string",
				"final_price": "string"
			}
		]
	}
}
```



