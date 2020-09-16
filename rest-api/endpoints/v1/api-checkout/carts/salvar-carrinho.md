---
description: Salvar as informações de um carrinho de compras.
---

# Salvar Carrinho

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/carts" %}
{% api-method-summary %}
Salvar carrinho
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint atualiza ou salva um carrinho de compras.
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
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="token" type="string" required=false %}
Token do carrinho de compras.
{% endapi-method-parameter %}

{% api-method-parameter name="domain" type="string" required=false %}
Domínio da loja cadastrada na XekoutApp.
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="attributes" type="string" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="original\_total\_price" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_price" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_discount" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="total\_weight" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="item\_count" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="items" type="array" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="requires\_shipping" type="boolean" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="items\_subtotal\_price" type="integer" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="cart\_level\_discount\_applications" type="array" required=false %}
Verificar documentação do Shopify.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 201014,
  "cart": {
    "cart_token": "string",
    "tenant_id": integer,
    "original_price": float,
    "item_count": integer,
    "created_at": timestamp,
    "updated_at": timestamp,
    "id": integer
  },
  "platform": integer
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 200004,
  "message": "Cart updated"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> Para verificar payload completo com suas definições, acesse a documentação fornecida pelo Shopify, a respeito da [referência da API do carrinho](https://shopify.dev/docs/themes/ajax-api/reference/cart).

{% hint style="warning" %}
As informações do carrinho poderão ser modificadas de acordo com a plataforma utilizada pelo lojista. Atualmente o sistema apenas utiliza o Shopify, mas futuramente serão adicionadas mais plataformas.
{% endhint %}

