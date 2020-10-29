# Cadastrar novo pedido

{% api-method method="get" host="https://api.xekout.app" path="/v2/auth/orders" %}
{% api-method-summary %}
Cadastrar novo pedidod
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint cria um novo pedido. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="domain" type="string" required=true %}
Domínio da loja cadastrada na Xekout.
{% endapi-method-parameter %}

{% api-method-parameter name="code" type="string" required=true %}
Cupom de desconto fornecido pelo lojista.
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
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
Token do carrinho do cliente.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="store" type="string" required=true %}
Dominio da loja em base64.
{% endapi-method-parameter %}

{% api-method-parameter name="customer\_id" type="number" required=true %}
Identificador do cliente cadastrado.
{% endapi-method-parameter %}

{% api-method-parameter name="shipping" type="object" required=true %}
Objeto com os dados de envio.
{% endapi-method-parameter %}

{% api-method-parameter name="discount" type="object" required=true %}
Objeto com os dados de desconto.
{% endapi-method-parameter %}

{% api-method-parameter name="cart" type="object" required=true %}
Objeto com dados do carrinho.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "success": true,
  "code": 201902,
  "status": "success",
  "order": {
    "id": number,
    "frete": integer,
    "frete_name": "string",
    "subtotal": integer,
    "total": integer,
    "cart_token": "string",
    "shopify_order_id": number,
    "shopify_url": "string"
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
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Payload completo das informações:

```text
{
	"cart_shopify": {
		"token": "6d8200ec514c7dbccd5997818021f126",
		"note": null,
		"attributes": {
		},
		"original_total_price": 21300,
		"total_price": 21300,
		"total_discount": 0,
		"total_weight": 0.0,
		"item_count": 1,
		"items": [
			{
				"id": 36209358241946,
				"properties": null,
				"quantity": 1,
				"variant_id": 36209358241946,
				"key": "36209358241946:9961d47281747d807f84f62e2067509f",
				"title": "Camisa",
				"price": 21300,
				"original_price": 21300,
				"discounted_price": 21300,
				"line_price": 21300,
				"original_line_price": 21300,
				"total_discount": 0,
				"discounts": [
				],
				"sku": "",
				"grams": 0,
				"vendor": "testeappstore6",
				"taxable": true,
				"product_id": 5731494920346,
				"product_has_only_default_variant": true,
				"gift_card": false,
				"final_price": 21300,
				"final_line_price": 21300,
				"url": "/products/camisa?variant=36209358241946",
				"featured_image": {
					"aspect_ratio": null,
					"alt": null,
					"height": null,
					"url": null,
					"width": null
				},
				"image": null,
				"handle": "camisa",
				"requires_shipping": true,
				"product_type": "",
				"product_title": "Camisa",
				"product_description": "",
				"variant_title": null,
				"variant_options": [
					"Default Title"
				],
				"options_with_values": [
					{
						"name": "Title",
						"value": "Default Title"
					}
				],
				"line_level_discount_allocations": [
				],
				"line_level_total_discount": 0
			}
		],
		"requires_shipping": true,
		"currency": "BRL",
		"items_subtotal_price": 21300,
		"cart_level_discount_applications": [
		]
	},
	"discount": null,
	"shipping": {
		"code": "Correios",
		"name": "Correios",
		"price": "1.00",
		"source": "shopify"
	},
	"customer_id": 1,
	"store": "dGVzdGVhcHBzdG9yZTYubXlzaG9waWZ5LmNvbQ=="
}
```



