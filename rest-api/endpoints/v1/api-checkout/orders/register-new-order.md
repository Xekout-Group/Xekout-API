# Cadastrar novo pedido

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/orders" %}
{% api-method-summary %}
Cadastrar novo pedido
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite cadastar um novo pedido.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter name="Cookies" required=true %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" %}
Identificador do estado enviado no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="order" required=true type="string" %}
Objeto contendo as informações do pedido.
{% endapi-method-parameter %}

{% api-method-parameter name="store" required=true type="string" %}
Domínio da loja codificado em base64.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
	"code": 200101,
	"status": "success",
	"orderSave": {
		"id": integer,
		"email": "string",
		"closed_at": null,
		"created_at": timestamp,
		"updated_at": timestamp,
		"number": integer,
		"note": null,
		"token": "string",
		"gateway": "string",
		"test": boolean,
		"total_price": "string",
		"subtotal_price": "string",
		"total_weight": integer,
		"total_tax": "string",
		"taxes_included": boolean,
		"currency": "string",
		"financial_status": "string",
		"confirmed": boolean,
		"total_discounts": "string",
		"total_line_items_price": "string2",
		"cart_token": null,
		"buyer_accepts_marketing": boolean,
		"name": "string",
		"referring_site": null,
		"landing_site": null,
		"cancelled_at": null,
		"cancel_reason": null,
		"total_price_usd": "string",
		"checkout_token": null,
		"reference": null,
		"user_id": null,
		"location_id": null,
		"source_identifier": null,
		"source_url": null,
		"processed_at": timestamp,
		"device_id": null,
		"phone": null,
		"customer_locale": null,
		"app_id": integer,
		"browser_ip": null,
		"landing_site_ref": null,
		"order_number": integer,
		"discount_applications": [
			{
				"type": "string",
				"value": "string",
				"value_type": "string",
				"allocation_method": "string",
				"target_selection": "string",
				"target_type": "string",
				"description": "string",
				"title": "string"
			}
		],
		"discount_codes": [
			{
				"code": "string",
				"amount": "string",
				"type": "string"
			}
		],
		"note_attributes": [
			{
				"name": "string",
				"value": "string"
			}
		],
		"payment_gateway_names": [],
		"processing_method": "string",
		"checkout_id": null,
		"source_name": "string",
		"fulfillment_status": null,
		"tax_lines": [],
		"tags": "string",
		"contact_email": "string",
		"order_status_url": "string",
		"presentment_currency": "string",
		"total_line_items_price_set": {
			"shop_money": {
				"amount": "string",
				"currency_code": "string"
			},
			"presentment_money": {
				"amount": "string",
				"currency_code": "string"
			}
		},
		"total_discounts_set": {
			"shop_money": {
				"amount": "string",
				"currency_code": "string"
			},
			"presentment_money": {
				"amount": "string",
				"currency_code": "string"
			}
		},
		"total_shipping_price_set": {
			"shop_money": {
				"amount": "string",
				"currency_code": "string"
			},
			"presentment_money": {
				"amount": "string",
				"currency_code": "string"
			}
		},
		"subtotal_price_set": {
			"shop_money": {
				"amount": "string",
				"currency_code": "string"
			},
			"presentment_money": {
				"amount": "string",
				"currency_code": "string"
			}
		},
		"total_price_set": {
			"shop_money": {
				"amount": "string",
				"currency_code": "string"
			},
			"presentment_money": {
				"amount": "string",
				"currency_code": "string"
			}
		},
		"total_tax_set": {
			"shop_money": {
				"amount": "string",
				"currency_code": "string"
			},
			"presentment_money": {
				"amount": "string",
				"currency_code": "string"
			}
		},
		"line_items": [],
		"fulfillments": [],
		"refunds": [],
		"total_tip_received": "0.0",
		"original_total_duties_set": null,
		"current_total_duties_set": null,
		"admin_graphql_api_id": "string,
		"shipping_lines": [],
		"billing_address": {
			"first_name": "teste",
			"address1": "string",
			"phone": "string",
			"city": "string",
			"zip": "string",
			"province": "string",
			"country": "string",
			"last_name": "string",
			"address2": "string",
			"company": "string",
			"latitude": float,
			"longitude": float,
			"name": "string",
			"country_code": "string",
			"province_code": "string"
		},
		"customer": {
			"id": integer,
			"email": "test@gmail.com",
			"accepts_marketing": boolean,
			"created_at": timestamp,
			"updated_at": timestamp,
			"first_name": "string",
			"last_name": "string",
			"orders_count": integer,
			"state": "string",
			"total_spent": "string",
			"last_order_id": integer,
			"note": null,
			"verified_email": boolean,
			"multipass_identifier": null,
			"tax_exempt": boolea,
			"phone": null,
			"tags": "string",
			"last_order_name": "string",
			"currency": "string",
			"accepts_marketing_updated_at": integer,
			"marketing_opt_in_level": "single_opt_in",
			"tax_exemptions": [],
			"admin_graphql_api_id": "integer",
			"default_address": {
				"id": integer,
				"customer_id": integer,
				"first_name": "string",
				"last_name": "string",
				"company": "string",
				"address1": "string",
				"address2": "string",
				"city": "string",
				"province": "string",
				"country": "string",
				"zip": "string",
				"phone": "string",
				"name": "string",
				"province_code": "string",
				"country_code": "string",
				"country_name": "string",
				"default": boolean
			}
		}
	}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 400000,
  "status": "error",
  "message": "User don't registered"
}

{
  "code": 400000,
  "status": "error",
  "message": "Tenant not found"
}

{
  "code": 400000,
  "status": "error",
  "message": "Invalid card brand"
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
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Abaixo modelo completo do objeto _**order**_, o mesmo pode variar de acordo com a forma de pagamento utilizada.

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



