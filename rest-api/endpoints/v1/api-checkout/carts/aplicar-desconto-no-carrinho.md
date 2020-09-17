---
description: Aplicar desconto no carrinho do cliente.
---

# Aplicar desconto no carrinho

{% api-method method="get" host="https://api.xekout.app" path="/v1/shopify/discount/:store\_domain/code" %}
{% api-method-summary %}
Aplicar desconto
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint aplica desconto no carrinho do cliente. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="store\_domain" type="string" required=true %}
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 200100,
  "status": "success",
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
    ]
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 400100,
  "status": "error",
  "message": "Price rule not exist"
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
  "code": 404100,
  "status": "error",
  "message": "Not Found"
}

{
  "code": 404100,
  "status": "error",
  "message": "Error on try get discount info"
}

{
  "code": 404100,
  "status": "error",
  "message": "Cart not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="danger" %}
O valor no campo code sempre precisa ser enviado codificado no formato base64. O não envio nesse formato resultará em respota HTTP 404.
{% endhint %}

{% hint style="warning" %}
Por default quando a requisição é chamada sem o envio de um cupom de desconto, é enviado no parâmetro \`code\` o valor padrão _**NONE**_ o que retorna o objeto do carrinho convertido.
{% endhint %}



