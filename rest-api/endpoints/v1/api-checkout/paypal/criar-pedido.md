# Criar pedido PayPal

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/orders/paypal" %}
{% api-method-summary %}
Criar pedido no PayPal
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint executar um pagamento para pedido utilizando PayPal.
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

{% api-method-parameter name="X-Request-Number" required=true %}
Identificador do estado enviado no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="store" required=true type="string" %}
Domínio da loja codificado em base64.
{% endapi-method-parameter %}

{% api-method-parameter name="order" required=true type="object" %}
Objeto contendo as informações do pedido.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
	"code": 201000,
	"status": "success",
	"order": {
		"id": integer,
		"payment_id": "string",
		"approval_url": {
			"href": "string",
			"rel": "string",
			"method": "string"
		},
		"user": {
			"first_name": "string",
			"last_name": "string",
			"document": "string",
			"country": "string",
			"email": "string"
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
  "message": "Error on try register paypal order"
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

Abaixo modelo completo do objeto _**order**_.

```text
{
	"paymentType": {
		"id": integer,
		"code": "string",
		"name": "string"
	},
	"gatewayType": {
		"id": integer,
		"code": "string"
	},
	"note": "string",
	"customer": {
		"id": integer
	},
	"shipping": boolean,
	"cart": {
		"total_cart_price": "string",
		"total_cart_discount": "string",
		"final_cart_price": "string",
		"currency": "string",
		"discount": "string",
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
		],
		"cart_token": "string"  	 op[]\ ,
		"shipping": null
	}
}
```

